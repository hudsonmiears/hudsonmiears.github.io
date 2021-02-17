---
id: 169
title: Portfolio
date: 2019-07-09T12:02:07+00:00
author: hudsonmiears
layout: page
permalink: /portfolio/
guid: https://hudsonmiears.com/?page_id=169
---
This is where I share gifs and demos of what I've been working on!

I'm happy to share the source code for any of these projects if you like, just let me know at hudson@hudsonmiears.com!

## Gameplay

### Roller Ball Kart Demo

-----|-----
![Loop-de-loops](/wp-content/uploads/2020/09/kart_racer_v_0_0_3_loop.gif)|![Countersteering](/wp-content/uploads/2020/09/kart_racer_v_0_0_5_countersteering-2.gif)
Loop-de-loops | Countersteering
![Driving on the wall](/wp-content/uploads/2020/09/kart_racer_v_0_0_7_driving_on_wall-1.gif)|![Local splitscreen](/wp-content/uploads/2020/09/kart_racer_v_0_0_5_splitscreen-3.gif)
Driving on the wall | Local splitscreen


<p class="has-medium-font-size">
  <a href="https://reizoukin.itch.io/kart-racer-demos">Play Here</a>
</p>

At the beginning of the year I spent several weeks prototyping some fun karting movement in Unity based on a technique described by [Kenney](https://twitter.com/kenneynl/status/1107783904784715788?lang=en). The results are super satisfying and I would really love to turn this into a Diddy Kong Racing-style racing adventure game one day, given the opportunity.

### Cabooze

<video preload="metadata"  loop="loop" width="100%" height="512" controls >
  <source src="/demos/CaboozeDemoJanuaryMp4.mp4" type="video/mp4">
</video>
Cabooze features fun use of cinemachine cameras and point-and-click movement.

Cabooze is my ongoing project which I've been documenting with dev logs on my YouTube channel. The end goal is to create a short, narrative game inspired by Spiritfarer, Paper Mario, and classic Point-and-clicks. The game will feature small minigames to represent different steps in the beer-brewing process. Keep up to date [here](https://www.youtube.com/channel/UCpHSXFLxATDubOAje6dDKeg?view_as=subscriber).

### Hoverbike Demo

<video autoplay="autoplay" loop="loop" width="100%" height="512" controls >
  <source src="/wp-content/uploads/2019/07/smoothernow.mp4" type="video/mp4">
</video>

Before I created the rolling ball motorcycle controller above, I experimented with using hover car physics, ie. adding upward forces to the motorcycle based on raycasts aimed at the ground. The results were pretty satisfying, but too bouncy for my tastes. Nevertheless I can see this being a fun, sci-fi style bike controller for a future project.

### Third Person Camera Controller.

![](/wp-content/uploads/2019/07/thirdpersoncameracontroller.gif)

Cameras are important in games, and I think about them a lot. In this demo I wanted to see what it would take to create a _good_ third person camera controller, inspired by [this talk by John Nesky](https://youtu.be/C7307qRmlMI). I did this while trying to emulate the movement of the old Star Fox games.

The camera moves in relation with the ship's movements. In addition, I used the idea of raycast &#8216;whiskers' from the talk. This way, the camera moves away from obstructions that it anticipates ahead of the ship. If you move too close to a wall, the camera moves away from it. It also averages this obstruction avoidance so that it centers out in narrow corridors.

Unfortunately, I discovered Unity's Cinemachine shortly after creating this, but I'm really proud of this demo; I think it's a great combination of programming and design decisions!

## UI Experiments

### Text message dialogue with Yarnspinner<figure class="wp-block-image">

![](/wp-content/uploads/2020/09/messageswithyarnspinner3-1.gif)

UI in Unity has always been a struggle for me, so I decided to go all in on a complex demo. The text is supplied by [Yarnspinner](https://yarnspinner.dev/), which is fairly painless to use and quick to set up. The message bubbles are positioned manually every update. Perhaps the hardest part of this project was sizing the text bubbles dynamically, which involves some strange interactions between components and children in Unity.

### Smartphone UI

![](/wp-content/uploads/2019/07/fakephonewithcamera.gif)

This was another, earlier attempt to learn UI in Unity, and I think the results speak for themselves. All of this is built with the standard Unity UI and a render texture; the phone's clock comes from the System time.

## Other stuff

### ARCore + Unity Dissertation Project

<a href="http://www.youtube.com/watch?feature=player_embedded&v=b8h-r0bhitY
" target="_blank"><img src="http://img.youtube.com/vi/b8h-r0bhitY/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a>

_This video demonstrates uploading and downloading object positions to and from the cloud._

My dissertation project was well documented, and you can find dev logs for it [on my blog](https://hudsonmiears.com/blog/). On the Unity side of things, the challenge was to develop an AR experience that keeps objects consistently in the same place in a small environment. 

The project as a whole focused on UX design and phenomenology. As I move into the future, I'm certainly interested in pursuing these ideas further and in different directions!

### ArcGIS Runtime SDK &#8211; Android samples

For the first six months at my current job, I worked on the ArcGIS Runtime SDK for Android Samples team. Many of the Kotlin samples were written by me. A challenge on this team was writing samples that were minimalistic and didn't include too much non-ArcGIS code, while also keeping UI intuitive and straightforward to use. I introduced some new techniques from Material design for this, such as the morphing FAB and bottom sheets, as well as some Kotlin-y techniques for front-loading the samples with ArcGIS code. I'm particularly proud of these samples: [1](https://github.com/Esri/arcgis-runtime-samples-android/tree/master/kotlin/manage-operational-layers), [2](https://github.com/Esri/arcgis-runtime-samples-android/tree/master/kotlin/find-route), and [3](https://github.com/Esri/arcgis-runtime-samples-android/tree/master/kotlin/group-layers).

### Game Jam Games

Game jams are great, and I've had a lot of fun participating in Ludum Dare, Global Game Jam, and others through my development journey.

<iframe src="https://itch.io/embed/778731" width="552" height="167" frameborder="0"><a href="https://thrasher08.itch.io/king-fisher">King Fisher by Thrasher08, fricochet, autumnpioneer, Hudson Miears, katieemmaw</a></iframe>

Above is our entry to the Wholesome Game Jam, a 48 hour jam in October 2020. I worked as the main programmer on the team and I was quite proud of the fishing mechanics.

<p style="text-align:left">
  The challenge with game jams is scope, and so all of these projects are quite small. I would note three games from Ludum Dare here:
</p>

**[OnFuelDrain()](https://quietaria.itch.io/onfueldrain)**, a space shoot-em-up where getting hit refuels your ship. 

**[Hug Me I'm Cold](https://reizoukin.itch.io/hug-me-im-cold)**, a short survival game where wearing too many sweaters to keep yourself warm also slows you down.

**[Oh no!](https://quietaria.itch.io/oh-no-the-sky-is-falling)**, a multiplayer turn-based combat game where you have to claim land and destroy enemy balloons.