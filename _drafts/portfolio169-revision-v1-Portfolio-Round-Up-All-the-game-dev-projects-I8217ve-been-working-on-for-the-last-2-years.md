---
id: 182
title: 'Portfolio Round Up: All the (game dev) projects I've been working on for the last 2 years'
date: 2019-07-09T12:32:14+00:00
author: hudsonmiears
layout: revision
guid: https://hudsonmiears.com/2019/07/09/169-revision-v1/
permalink: /2019/07/09/169-revision-v1/
---
While learning game development and Unity for the last two years, I've tried my hand at creating a lot of things. Most of these things are gameplay tests, and I wanted to compile them all together to show the cool things I've done (which can be sometimes difficult to display).

My focus for all my projects is to make interesting gameplay mechanics and learn the depths of Unity. I feel confident now with my knowledge of Unity, and I'm ready to work on some big projects! 

I'm happy to share the source code for any of these projects if you like, just let me know at hudson@hudsonmiears.com!

### Third Person Camera Controller.

<div class="wp-block-image">
  <figure class="aligncenter"><img src="/wp-content/uploads/2019/07/thirdpersoncameracontroller.gif" alt="" class="wp-image-155" /></figure>
</div>

Cameras are important in games, and I think about them a lot. In this demo I wanted to see what it would take to create a _good_ third person camera controller, inspired by [this talk by John Nesky](https://youtu.be/C7307qRmlMI). I did this while trying to emulate the movement of the old Star Fox games.

The movement itself is achieved my aiming the ship at a target with an offset ahead of the ship. There's some artificial rolling there, too.

The camera moves in relation with the ship's movements. In addition, I used the idea of raycast &#8216;whiskers' from the talk. This way, the camera moves away from obstructions that it anticipates ahead of the ship. If you move too close to a wall, the camera moves away from it. It also averages this obstruction avoidance so that it centers out in narrow corridors.

I'm really proud of this demo; I think it's a great combination of programming and design decisions! 

### ARCore + Unity Dissertation Project<figure class="wp-block-embed-youtube wp-block-embed is-type-video is-provider-youtube wp-embed-aspect-4-3 wp-has-aspect-ratio">

<div class="wp-block-embed__wrapper">
</div><figcaption> 

_This video demonstrates uploading and downloading object positions to and from the cloud._ </figcaption></figure> 

My dissertation project has been well documented so far, and you can find dev logs for it [on my blog](https://hudsonmiears.com/blog/). On the Unity side of things, the challenge is to develop an AR experience that keeps objects consistently in the same place in a small environment. It's still a challenge, but I've been making steady progress and I invite you to take a look at the logs.

The project as a whole is focused on UX design and phenomenology. As I move into the future, I'm certainly interested in pursuing these ideas further and in different directions!

### Hoverbike Demo<figure class="wp-block-video aligncenter"><video controls src="/wp-content/uploads/2019/07/smoothernow.mp4"></video></figure> 

I really like playing with fake physics, because the veneer of physics is often more important than simulation. Hovercar tutorials are ubiquitous online! But the only thing cooler than a hovercar is a hoverbike.

The problem with bikes, of course, is that they have fewer points of contact with the ground than do cars. And what's more, simulating the powersteering and roll effects of a bike were the important factors to me. That's hard!

I actually use six hoverpoints for this hoverbike, four of which are angled out from the bike to stabilize it. The bike is always trying to right itself, and I manually roll it whenever it turns. This makes it look like a naturally turning bike, but in reality all the turning is done with a y-axis rotation.

It took a lot of fidding to get it to feel like it does. There are definitely improvements to be made! It still struggles with bumpy terrain and turning at high speeds, but I'm satisfied with the current prototype.

### Game Jam Games

Game jams are great, and I've had a lot of fun participating in Ludum Dare, Global Game Jam, and others through my development journey.

The challenge with game jams is scope, and so all of these projects are quite small. I would note three games from Ludum Dare here:

**[OnFuelDrain()](https://quietaria.itch.io/onfueldrain)**, a space shoot-em-up where getting hit refuels your ship. 

**[Hug Me I'm Cold](https://reizoukin.itch.io/hug-me-im-cold)**, a short survival game where wearing too many sweaters to keep yourself warm also slows you down.

**[Oh no!](https://quietaria.itch.io/oh-no-the-sky-is-falling)**, a multiplayer turn-based combat game where you have to claim land and destroy enemy balloons.

### A Game By Its Cover&#8211;Current project

<div class="wp-block-image">
  <figure class="aligncenter"><img src="/wp-content/uploads/2019/07/fakephonewithcamera.gif" alt="" class="wp-image-151" /><figcaption><em>The game will feature a fake phone with its own camera.</em></figcaption></figure>
</div>

My current project is being made for [A Game By Its Cover jam](https://itch.io/jam/a-game-by-its-cover-2019). Inspired by [this famicase cartridge](http://www.translatetheweb.com/?from=&to=en&dl=en&a=http%3A%2F%2Ffamicase.com%2F13%2Fsofts%2F58.html), the game will consist of searching through a forest to find and record a video of bigfoot. At its current stage, I've been working on creating an in-game phone to use as the user interface. 

You can track my progress on [twitter](https://twitter.com/hudsonmiears/media)! As I'm only working on it in my off-time, it's slow development, but so far I'm quite excited to be working with Unity's UI system, render textures, replacement shaders, and a more polished experience than I've worked on before.