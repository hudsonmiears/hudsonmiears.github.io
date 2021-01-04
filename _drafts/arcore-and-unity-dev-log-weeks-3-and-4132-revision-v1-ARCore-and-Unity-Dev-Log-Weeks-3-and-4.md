---
id: 134
title: 'ARCore and Unity Dev Log: Weeks 3 and 4'
date: 2019-06-18T10:07:13+00:00
author: hudsonmiears
excerpt: In weeks 3 and 4 of my ARCore and Unity dissertation project I spent most of my time developing a cloud storage save system for real-world locations.
layout: revision
guid: https://hudsonmiears.com/2019/06/18/132-revision-v1/
permalink: /2019/06/18/132-revision-v1/
---
My work over the last two weeks has been a bit sporadic, so I decided not to write up a dev log last week. Now that I've made a complete feature it feels like a good time to describe the progress so far.

If you are interested in learning more about the project, I would invite you to check out the [introduction](https://hudsonmiears.com/2019/05/28/arcore-and-unity-dev-log-introduction/). I also have dev logs for weeks [1](https://hudsonmiears.com/2019/05/28/arcore-and-unity-dev-log-week-1/) and [2](https://hudsonmiears.com/2019/06/04/arcore-and-unity-dev-log-week-2/).

My main focus for these two weeks has been to create a save and load system for the app. The idea is to have a similar system to [Cloud Anchors](https://codelabs.developers.google.com/codelabs/arcore-cloud-anchors/index.html#0), which are Google's solution to ensuring that two devices can look at the same AR scene simultaneously. Unfortunately, cloud anchors only work for 24 hours.

For this project, a key (in fact, foundational) component is that users should be able to walk into the garden, download the scene, and have the same experience. That is, objects in the AR scene should always be at the same real-world location, no matter what day the user is interacting with the app.

When I was researching the best way to do this, there were a few people online saying that the only way to make it work would be to save snapshots from the camera feed and use image recognition to determine what the camera is looking at. The idea here is that if you have four corners of a picture, then the device can cross-reference its own feed with the known pictures and determine where it is in the space. [This stackoverflow question](https://stackoverflow.com/questions/46304053/can-i-save-ar-data-for-reuse) has two answers that describe what I'm talking about.

This was way outside the scope of my project, and I had an inkling of a better idea. Based on my own understanding of ARCore, objects in the AR scene are in their own coordinate space just as any game would handle position information. If I have a known location in the real world, and I know where all of the objects should be placed relative to that location, can't I just repopulate the objects each session? All that needs to be done is to make sure that users start each session with their device in the same location.

Indeed, [some people on this github issue](https://github.com/google-ar/arcore-android-sdk/issues/94) have already mentioned this as a possibility, but I didn't find anybody who had shared exactly how to do that.<figure class="wp-block-image">

<img src="https://hudsonmiears.com/wp-content/uploads/2019/06/savingloading-1024x768.jpg" alt="" class="wp-image-133" srcset="https://hudsonmiears.com/wp-content/uploads/2019/06/savingloading-1024x768.jpg 1024w, https://hudsonmiears.com/wp-content/uploads/2019/06/savingloading-300x225.jpg 300w, https://hudsonmiears.com/wp-content/uploads/2019/06/savingloading-768x576.jpg 768w" sizes="(max-width: 1024px) 100vw, 1024px" /> <figcaption>Unexceptional thoughts only become unexceptional when they're written on paper.</figcaption></figure> 

#### Formatting

I decided to set to work with this easier, though more limiting, system. I noticed that the position of the camera when the app starts is always (0,0,0), which is a great help!

The first issue I noticed was that I wanted to use anchors (which ensure that objects stay &#8216;anchored' to the same place in the real world, ie. they don't drift when the camera moves). However, anchors cannot be created without a Trackable (an object such as a plane or point in the ARCore point cloud).

This is fine, as currently my objects are always placed on planes, but it definitely added some spice to the solution.

I came up with quite a hacky solution for my first step, which was to load up an object at runtime. I created a serializable `SavedDataObject` which stores the position, name, and other variables off an object I want to save. Next, I keep a reference to all of my `SavedDataObject`s in the `ObjectDataBundle`.

Then, at runtime, I have a GameObject called the Relocalizer which has the component `RelocalizationHandler`. The purpose of this script is to figure out what objects need to be placed in the world and then, of course, place them.

To achieve this, the `RelocalizationHandler` simply has a List of `SavedDataObject`s. It needs to create an anchor for each of these, so every frame it performs two raycasts (up and down) from the stored position. If it detects a plane, it creates an anchor and places the object at the stored location. The rest is essentially the same as the Google-provided `AndyPlacementManipulator` in the [Object Manipulation tutorial](https://github.com/google-ar/arcore-unity-sdk/blob/master/Assets/GoogleARCore/Examples/ObjectManipulation/Scripts/AndyPlacementManipulator.cs).

I noticed some problems with this, namely that stored and relocalized positions were pretty fuzzy. However, I wasn't too concerned for my purposes if the positions were a bit off; 0.1 units is not enough to be concerned about.

The biggest problem I noticed was actually something I've touched on before: because ARCore uses the camera feed to determine how it is moving in the world, moving the phone very quickly or covering the camera can cause objects to jump around or shift locations. This is true when the app starts up as well: if the camera is covered when the scene loads, it will be much less accurate than if it has a clear view. For this reason, when designing the real-world location for users to synchronize their phones, the phone should be set down vertically, with a clear and unobstructed view of the world.

#### Firebase

With this minor success (I was only using a single, faked `SavedDataObject` at this point) I decided to push it to Firebase and see if I could download the object and relocalize it. To do this, I made sure to serialize all of my objects from the `ObjectDataBundle` into a byte array. I had a ton of help from the wonderful [Brackey's video on saving and loading](https://www.youtube.com/watch?v=XOjd_qU2Ido&t=713s). Once I had the byte array, I could push it to Firebase using essentially the same code as I used for audio in Firebase in week 1. I decided at this point that the `ObjectDataBundle` would handle all of the serialization and deserialization, and the `RelocalizationHandler` would handle all of the Firebase communication and repopulation.

The only divergence from Brackey's code was that I didn't want to use a Filestream to store the byte array, as I only needed the files stored in Firebase and I have already discovered the difficulty of using Android's filesystem. Instead, I put the byte array into a MemoryStream, which worked out perfectly fine.

Then I set about downloading the file, and this was mostly trivial given that all I needed to do was deserialize the byte array to get my `SavedDataObject`s back.

#### Repopulating the world

The final step in this journey was to actually put the correct object in the correct location with the correct model and the correct audio reference. This took about a full day and wasn't without its obstacles.

The biggest obstacle was that I now needed to develop a system that would keep a reference to all of the objects that I want to save as they are being placed. Then I need to create `SavedDataObject`s for each of these.

I created a class `ObjectData` to solve this. The purpose of this class is to serve as an inbetween between Unity and the Serializable `SavedDataObject`, as types like Vector3 and Quaternion are not Serializable. Mainly, whenever an object is placed, an `ObjectData` component is added to it and saved. This creates a `SavedDataObject`. The `ObjectData` component then passes this to the `ObjectDataBundle` which checks if that object already exists in its cache and updates or adds it.

I find this solution to be a little bit messy, but it ended up working fine, and now that I have a proof of concept I can clean it up.

The final result was that I could place objects in the world, press save, close the app, open it again, press load, and then when the right plane is tracked, the objects are automatically placed there!

This is a great prototype, and once I've cleaned it up a little bit I plan to release it open source. I think, with a little bit of editing, this can be a useful system to anyone looking for a slightly imprecise but working alternative to Cloud Anchors.

### Everything else

Other than working on this storage solution, my time was devoted to revising my proposal and reading literature; there's not much to talk about there.

Looking forward, I'm not likely to be doing much development this week, though I may find some time to make exciting design decisions and tie up a few loose ends in the prototype. The project is hitting a point where it's time to put all of this theory into practice, and playing with ARCore is going to transform into actually working on the app and its functionality, rather than the technology.

Thanks for reading!