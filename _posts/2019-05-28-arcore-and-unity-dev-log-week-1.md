---
id: 114
title: 'ARCore and Unity Dev Log: Week 1'
date: 2019-05-28T12:03:37+00:00
author: hudsonmiears
excerpt: 'In this post I explain the initial setup and testing process for ARCore and Firebase in Unity3D. '
layout: post
guid: https://hudsonmiears.com/?p=114
permalink: /2019/05/28/arcore-and-unity-dev-log-week-1/
image: /wp-content/uploads/2019/05/IMG_20190528_115311-1-920x575.jpg
categories:
  - Design
  - Dev Log
tags:
  - ar
  - arcore
  - design
  - dev-log
  - firebase
  - unity
  - ux
---
If you haven&#8217;t read the introduction to this project, I recommend you take a look to get an idea of what I&#8217;m trying to do with AR. You can read it [here](https://hudsonmiears.com/2019/05/28/arcore-and-unity-dev-log-introduction/).

With any project I prefer to learn the basic technological tools that I have at my disposal first. I chose ARCore because I recently completed a group project using Android Studio, and I chose Unity because I&#8217;ve been using Unity for a long time and it&#8217;s a comfortable and familiar environment. On top of this, both of these technologies have a ton of resources available online, which eases the learning process. 

One of the biggest lessons I learned in the Android project was that time spent on learning is a crucial part of development time, so I really wanted to give some of the [Unity+ARCore tutorials](https://developers.google.com/ar/develop/unity/quickstart-android) a go. My focus for week one was to understand the basics of how ARCore works so that I could use that for design considerations later on. I want to build a minimum viable product first so that any design decisions I make are well-informed and don&#8217;t take excessive time to implement.

Of course, I started with a basic idea of what I want my ARCore app to look like. I created a rough flow diagram to visualize it below.<figure class="wp-block-image">

<img src="https://hudsonmiears.com/wp-content/uploads/2019/05/IMG_20190528_115311-1-1024x742.jpg" alt="" class="wp-image-116" srcset="https://hudsonmiears.com/wp-content/uploads/2019/05/IMG_20190528_115311-1-1024x742.jpg 1024w, https://hudsonmiears.com/wp-content/uploads/2019/05/IMG_20190528_115311-1-300x217.jpg 300w, https://hudsonmiears.com/wp-content/uploads/2019/05/IMG_20190528_115311-1-768x556.jpg 768w" sizes="(max-width: 1024px) 100vw, 1024px" /> <figcaption>Left: Admin use case. Right: Normal user.</figcaption></figure> 

The basic idea is this: admins will be able to place 3D models around the real world. Attached to the 3D models are audio recordings. Normal users will find the 3D models, &#8216;pick them up&#8217; (eg. by pinch-zooming), and listen to the audio recording through the small ear speaker.

The fundamental concept behind this idea is to create a digital layer to the real world which users can listen to. By making the information in audio-format, and ensuring that users use the small speaker to listen to them like a phone call, the users&#8217; eyes and thumbs will be left to interact with the garden itself (rather than the phone).

#### 21/5/19

On day one I dedicated myself to solely following Google&#8217;s ARCore tutorials for Unity. Setup can be a bit tedious; you have to ensure that you have the correct versions of the Android SDK, Unity, the ARCore SDK, a phone that can support AR, and you have to enter some settings to link everything together.

Once it&#8217;s setup, Google provides a few example scenes in Unity. The first is called HelloAR, and simply provides functionality for placing 3D models on planes in the world. Also included is a cloud anchor tutorial (which allows two users on different phones to see the same 3D models) and an object manipulation scene (which allows the user to scale, rotate, and translate the 3D objects).

After following these tutorials I felt I had a basic understanding of how ARCore keeps 3D models attached to real-world locations. The camera in the Unity scene gets its video feed from the device camera and moves around in the digital Unity world according to the device&#8217;s real-world movements. Google does some magic image analysis trickery to figure out where planes exist in the real-world, and I&#8217;m satisfied without knowing the details of that.

When creating an object, the app responds to a user&#8217;s tap by raycasting into the screen and then, conceptually, into the real world. If it hits a plane, then it&#8217;s a fine location to place a 3D model.

Whenever an object is placed in the world, an anchor is created. An anchor is a parent transform object which has logic to keep it &#8216;anchored&#8217; to a real-world location. In actuality, the anchor is moving relative to the device movements: if the device moves to the right, then all the anchors move to the left. Anchors are created via poses; a pose seems to be conceptually similar to a transform, but instead of being in Unity world-space, it&#8217;s located in real-world-space.

Finally, the object is made a child of the anchor.

With this knowledge in my head, I was able to get a better idea of how ARcore works and how I would be able to think about creating the app.

#### 22/5/19

Day 2 mostly consisted of reviewing the [Object Manipulation example](https://developers.google.com/ar/develop/unity/tutorials/object-manipulation-sample) scene. This was a bit more complicated as objects that are already place now need to be interacted with, which means more logic for detecting what&#8217;s being tapped and how to move things around in the real world.

Google achieves this with a Manipulation System, which is a singleton class that passes all gesture inputs into Manipulators. Manipulators act as parent objects to anchors. Manipulator prefabs have components attached to them, also called manipulators, each of which contains the logic for a specific type of manipulation like scale, translate, or rotate.

I was feeling pretty confident after reviewing this code, and noted some thoughts down to myself, for example:

  * The pinch-zoom gesture can use the gap delta parameter (the distance between the two active fingers) to determine when it&#8217;s appropriate to play sound from the speaker. This would ensure that users complete the gesture before the app determines the intent of the action.
  * The app populates the Unity world with objects that are spaced relative to each other and to the camera. If this layout of objects can be saved on the cloud, then the world of objects can be shared by placing the device in a known location and populating the objects relative to that known location. This removes the need for GPS to determine where to place objects.
  * To &#8216;pick up&#8217; or zoom into an object that the user wants to interact with, the object should move towards the camera, saving its original location so that it can snap back later. Typically, zoom is accomplished in Unity by reducing the FOV of the camera, but this would cause problems when the device is going to be shaky and constantly moving.

#### 23/5/19

I switched things up on the third day by looking at how I would store information on the cloud. I needed to store the locations of objects and the audio files.

I had heard about [Firebase](https://firebase.google.com/) as a potential option, and I found that [Firebase storage](https://firebase.google.com/products/storage/) was compatible with Unity and could easily store audio files. I&#8217;m not extremely familiar with setting up databases and networking, so I wanted to have the easiest solution possible.

I also spent some time reading an article from 2003 by Persson et al. entitled [_GeoNotes: A Location-Based Information System for Public Spaces_.](https://www.researchgate.net/publication/226938773_GeoNotes_A_Location-Based_Information_System_for_Public_Spaces) The researchers describe a conceptually similar application for older phones using text annotations and GPS coordinates. Of particular note was the idea of annotations that decay and how they incorporated deixis into the app; annotations placed in real-world locations have the capability of referring directly to the real world with words like &#8216;this table&#8217; and &#8216;that watercooler&#8217;. They also note:<span style="text-decoration: underline;"></span><span style="text-decoration: underline;"></span>

<blockquote class="wp-block-quote">
  <p>
    &#8220;To maximize visibility, annotations are often placed in passageways.&#8221;
  </p>
  
  <p>
    &#8220;Without some form of social feedback, opening up to the socio-public space will be a waste of energy.&#8221;
  </p>
  
  <p>
    &#8220;professionally created information often tends to be &#8216;serious&#8217; or &#8216;utility oriented&#8217; in ways in which post-its, graffiti, tagging and posters are not. In those systems, the social, expressive and subversive functions of analog annotation technologies tend to be overlooked.&#8221;
  </p>
  
  <cite>Persson et al. (2003). In <em>Designing Information Spaces: The Social Navigation Approach.</em></cite>
</blockquote>

These insights will be extremely useful to the design process later on, and are useful to think about even at this early stage of the project.

#### 24/5/19

Day four was quite productive, as I decided to take a break from tutorials and try to implement something more substantial. My goal for the day was to modify Google&#8217;s Object Manipulation example scripts to move objects close to the camera when the pinch gesture was used.

The main focus of my code was in the Scale Manipulator script provided. I added a line in OnEnable to cache the initial position of the object in the world. Next, I needed to calculate where the object would be moving towards. I do this by getting the camera position and the camera&#8217;s forward vector. Then I project an offset (because I don&#8217;t want the object to engulf the camera) onto the camera&#8217;s forward and use that as the final position. This final position is calculated in OnContinueManipulation, which is run every frame of the manipulation.

I use Vector3.Lerp to actually move the object. This is why it was important to know the two endpoints of the movement; I didn&#8217;t want to be moving the object infinitesimally closer to the camera each frame.

I found that ARCore positioning can be quite unreliable, even with a good camera. Fast movements or camera obstructions can cause objects to jump around, and positions did not seem to be consistently updated. Plane detection can fail sometimes as well.

After implementing the movement code, I wanted objects to &#8216;lock&#8217; to the camera and &#8216;unlock&#8217; when the user was finished with them. This would solve the problem of camera movement: once an object crosses a threshold and is close enough to the camera, it would child itself to the camera&#8217;s transform and move around with it. This was done to make it seem as if the user picked up the object as well as to ensure that the object doesn&#8217;t simply hang in space where the camera was located a few frames ago.

I used the clamped scale ratio parameter provided in Google&#8217;s script; this is essentially a float between 0 and 1 that describes how far the user has moved their fingers apart, with 0 being no movement and 1 being maximum movement. This float became the threshold for locking the object to the camera: if it passes 0.75, then the user wants to pick the object up.

This works fine, but there are still some issues with object orientation and positioning. Perhaps a better solution would be to have a defined transform as a child of the camera in Unity which would become the lock point.

Finally, if the user pinches the object and crosses the threshold below 0.75, the object bounces back to its original position.

The biggest issue I have had with this system is that objects can still be placed in the world while another object is locked to the camera. This causes the locked object to be deselected, which makes it nearly impossible to unlock the object. Thus, the object remains obstructing the screen.

In order to solve this problem, however, I will have to learn more about how object selection and the provided Manipulation System work.

#### 27/5/19

For the final day of the week I turned back to Firebase to attempt to integrate it into the app. This was mainly done as a learning exercise to ensure that Firebase would be as simple as expected.

I started by setting up Firebase, which is a much lengthier process than setting up ARCore as it requires setting up a project on the Firebase console, creating a keystore and key in Unity for secure connections, downloading and installing various SDKs and ensuring that certain settings all match between the various tools.

Once this was all done, I created an initialization script which I simply attached to the &#8220;ARCore device&#8221; in my Unity scene. I chose this object because it already had one component, the Manipulation System, which runs as soon as the app starts. I used Google&#8217;s provided script for initializing Firebase and shoved it into the Awake method of the component. This turned out to work just fine.

I chose Firebase storage over the other options as this was the one that directly advertised easy storage of audio files. Firebase storage works more like Google Drive than any database I&#8217;ve interacted with; it is structured simply as a file system like on Linux. You can easily upload files themselves or byte arrays to the storage space.

I decided to test the system by storing a test mp3 in my StreamingAssets folder in Unity. Unfortunately I had no idea of the complications of accessing files in Unity on Android. My knowledge is a bit spotty, but my understanding is that it has to be done through some sort of server running on the Android device. [I found some code online](https://gist.github.com/amowu/8121334) that makes it pretty simple and used that. This let me transfer the byte array read from the Android file sytem into the Firebase storage I had set up (using the code that Google provided).

I&#8217;m not too worried about understanding the vast depth of this file management, as I expect that I won&#8217;t be touching Android&#8217;s file system for this project. In future I expect to be using a byte array stored in memory from Unity&#8217;s microphone class; user&#8217;s won&#8217;t be storing audio files on their own devices. Of course, it remains to be seen whether audio recording will be so simple in Unity (it probably won&#8217;t).

It took a good bit of banging together, but eventually I managed to get the audio file correctly uploaded to the cloud and could listen to it on my computer. Success! I was about to dive into downloading the file back into the app&#8217;s memory, only to discover that I had no clue how to pass a byte array back into Unity and parse it as an audio file.

Oh well, that&#8217;s for another day.

#### Review

So far it looks like week 1 was fairly successful; the bones of the app are in place. There will certainly be some difficulties to be overcome with audio files and storing object placement. However, the choice not to use a GPS system or an SQL database will certainly make this project go much quicker than expected.

Firebase and ARCore are well documented, if a bit confusing to first-time users. However, following the tutorials makes it fairly simple to go from no-knowledge-about-AR to actually making something that works. It&#8217;s an exciting domain!

For the next week I&#8217;ll be looking at downloading that file from Firebase again and tuning up the object manipulations, though some time will definitely be spent on research. I can see the meat of the design process ahead, and it will be exciting to put all of the theory I discussed in the intro into practice.

Thanks for reading!