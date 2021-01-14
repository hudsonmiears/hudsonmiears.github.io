---
id: 256
title: 'What I've been working on'
date: 2020-10-14T07:45:37+00:00
author: hudsonmiears
layout: revision
guid: https://hudsonmiears.com/2020/10/14/169-revision-v1/
permalink: /2020/10/14/169-revision-v1/
---
This is where I share gifs and demos of what I've been working on!

I'm happy to share the source code for any of these projects if you like, just let me know at hudson@hudsonmiears.com!

## Gameplay

### Roller Ball Kart Demo

<ul class="wp-block-gallery columns-3 is-cropped">
  <li class="blocks-gallery-item">
    <figure><img src="/wp-content/uploads/2020/09/kart_racer_v_0_0_3_loop-1.gif" alt="" data-id="232" data-link="https://hudsonmiears.com/portfolio/kart_racer_v_0_0_3_loop-1/" class="wp-image-232" /><figcaption>Loop-de-loops</figcaption></figure>
  </li>
  <li class="blocks-gallery-item">
    <figure><img src="/wp-content/uploads/2020/09/kart_racer_v_0_0_5_countersteering-2.gif" alt="" data-id="233" data-link="https://hudsonmiears.com/portfolio/kart_racer_v_0_0_5_countersteering-2/" class="wp-image-233" /><figcaption>Countersteering</figcaption></figure>
  </li>
  <li class="blocks-gallery-item">
    <figure><img src="/wp-content/uploads/2020/09/kart_racer_v_0_0_7_driving_on_wall-1.gif" alt="" data-id="234" data-link="https://hudsonmiears.com/portfolio/kart_racer_v_0_0_7_driving_on_wall-1/" class="wp-image-234" /><figcaption>Driving on the wall</figcaption></figure>
  </li>
  <li class="blocks-gallery-item">
    <figure><img src="/wp-content/uploads/2020/09/kart_racer_v_0_0_5_splitscreen-3.gif" alt="" data-id="230" class="wp-image-230" /><figcaption>Local splitscreen</figcaption></figure>
  </li>
</ul>

<p class="has-medium-font-size">
  <a href="https://reizoukin.itch.io/kart-racer-demos">Play Here</a>
</p>

At the beginning of the year I spent several weeks prototyping some fun karting movement in Unity based on a technique described by [Kenney](https://twitter.com/kenneynl/status/1107783904784715788?lang=en). The results are super satisfying and I would really love to turn this into a Diddy Kong Racing-style racing adventure game one day, given the opportunity.

### Cabooze<figure class="wp-block-embed-youtube wp-block-embed is-type-video is-provider-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio">

<div class="wp-block-embed__wrapper">
</div></figure> <figure class="wp-block-image">

<img src="/wp-content/uploads/2020/09/cinemachineshowoff.gif" alt="" class="wp-image-220" /> <figcaption>Cabooze features fun use of cinemachine cameras and point-and-click movement.</figcaption></figure> 

Cabooze is my ongoing project which I've been documenting with dev logs on my YouTube channel. The end goal is to create a short, narrative game inspired by Spiritfarer, Paper Mario, and classic Point-and-clicks. The game will feature small minigames to represent different steps in the beer-brewing process. Keep up to date [here](https://www.youtube.com/channel/UCpHSXFLxATDubOAje6dDKeg?view_as=subscriber).

### Hoverbike Demo<figure class="wp-block-video aligncenter"><video controls src="/wp-content/uploads/2019/07/smoothernow.mp4"></video></figure> 

Before I created the rolling ball motorcycle controller above, I experimented with using hover car physics, ie. adding upward forces to the motorcycle based on raycasts aimed at the ground. The results were pretty satisfying, but too bouncy for my tastes. Nevertheless I can see this being a fun, sci-fi style bike controller for a future project.

### Third Person Camera Controller.

<div class="wp-block-image">
  <figure class="aligncenter"><img src="/wp-content/uploads/2019/07/thirdpersoncameracontroller.gif" alt="" class="wp-image-155" /></figure>
</div>

Cameras are important in games, and I think about them a lot. In this demo I wanted to see what it would take to create a _good_ third person camera controller, inspired by [this talk by John Nesky](https://youtu.be/C7307qRmlMI). I did this while trying to emulate the movement of the old Star Fox games.

The movement itself is achieved my aiming the ship at a target with an offset ahead of the ship. There's some artificial rolling there, too.

The camera moves in relation with the ship's movements. In addition, I used the idea of raycast &#8216;whiskers' from the talk. This way, the camera moves away from obstructions that it anticipates ahead of the ship. If you move too close to a wall, the camera moves away from it. It also averages this obstruction avoidance so that it centers out in narrow corridors.

Unfortunately, I discovered Unity's Cinemachine shortly after creating this, but I'm really proud of this demo; I think it's a great combination of programming and design decisions!

## UI Experiments

### Text message dialogue with Yarnspinner<figure class="wp-block-image">

<img src="/wp-content/uploads/2020/09/messageswithyarnspinner3-1.gif" alt="" class="wp-image-218" /> </figure> 

UI in Unity has always been a struggle for me, so I decided to go all in on a complex demo. The text is supplied by [Yarnspinner](https://yarnspinner.dev/), which is fairly painless to use and quick to set up. The message bubbles are positioned manually every update. Perhaps the hardest part of this project was sizing the text bubbles dynamically, which involves some strange interactions between components and children in Unity.

### Smartphone UI

<div class="wp-block-image">
  <figure class="aligncenter"><img src="/wp-content/uploads/2019/07/fakephonewithcamera.gif" alt="" class="wp-image-151" /></figure>
</div>

This was another, earlier attempt to learn UI in Unity, and I think the results speak for themselves. All of this is built with the standard Unity UI and a render texture; the phone's clock comes from the System time.

## Other stuff

### ARCore + Unity Dissertation Project<figure class="wp-block-embed-youtube wp-block-embed is-type-video is-provider-youtube wp-embed-aspect-4-3 wp-has-aspect-ratio">

<div class="wp-block-embed__wrapper">
</div><figcaption> 

_This video demonstrates uploading and downloading object positions to and from the cloud._ </figcaption></figure> 

My dissertation project was well documented, and you can find dev logs for it [on my blog](https://hudsonmiears.com/blog/). On the Unity side of things, the challenge was to develop an AR experience that keeps objects consistently in the same place in a small environment. 

The project as a whole focused on UX design and phenomenology. As I move into the future, I'm certainly interested in pursuing these ideas further and in different directions!

### ArcGIS Runtime SDK &#8211; Android samples

For the first six months at my current job, I worked on the ArcGIS Runtime SDK for Android Samples team. Many of the Kotlin samples were written by me. A challenge on this team was writing samples that were minimalistic and didn't include too much non-ArcGIS code, while also keeping UI intuitive and straightforward to use. I introduced some new techniques from Material design for this, such as the morphing FAB and bottom sheets, as well as some Kotlin-y techniques for front-loading the samples with ArcGIS code. I'm particularly proud of these samples: [1](https://github.com/Esri/arcgis-runtime-samples-android/tree/master/kotlin/manage-operational-layers), [2](https://github.com/Esri/arcgis-runtime-samples-android/tree/master/kotlin/find-route), and [3](https://github.com/Esri/arcgis-runtime-samples-android/tree/master/kotlin/group-layers).

### Game Jam Games

Game jams are great, and I've had a lot of fun participating in Ludum Dare, Global Game Jam, and others through my development journey.<figure></figure> 

Above is our entry to the Wholesome Game Jam, a 48 hour jam in October 2020. I worked as the main programmer on the team and I was quite proud of the fishing mechanics.

<p style="text-align:left">
  The challenge with game jams is scope, and so all of these projects are quite small. I would note three games from Ludum Dare here:
</p>

**[OnFuelDrain()](https://quietaria.itch.io/onfueldrain)**, a space shoot-em-up where getting hit refuels your ship. 

**[Hug Me I'm Cold](https://reizoukin.itch.io/hug-me-im-cold)**, a short survival game where wearing too many sweaters to keep yourself warm also slows you down.

**[Oh no!](https://quietaria.itch.io/oh-no-the-sky-is-falling)**, a multiplayer turn-based combat game where you have to claim land and destroy enemy balloons.