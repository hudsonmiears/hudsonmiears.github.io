---
title: Things I've made
author: hudsonmiears
layout: page
permalink: /portfolio/
---
This is where I share gifs and demos of what I’ve been working on!

I’m happy to share the source code for any of these projects if you like, just let me know at hudson@hudsonmiears.com!

<em>Click on any of the tabs below to see some footage.</em>

<script src="{{ base.url | prepend: site.url }}/demos/tabs.js"></script>
<link rel="stylesheet" href="{{ base.url | prepend: site.url }}/demos/tabs.css">

<div class="tab">
  <button class="tablinks" onclick="openSection(event, 'Movement')" id="defaultOpen">Movement</button>
  <button class="tablinks" onclick="openSection(event, 'Cameras')">Cameras</button>
  <button class="tablinks" onclick="openSection(event, 'Dialogue')">Dialogue</button>
  <button class="tablinks" onclick="openSection(event, 'UI')">UI</button>
  <button class="tablinks" onclick="openSection(event, 'Post-processing')">Post-processing</button>
  <button class="tablinks" onclick="openSection(event, 'Software-development')">Software Development</button> 
</div>

<script>
// Get the element with id="defaultOpen" and click on it
document.getElementById("defaultOpen").click();
</script>

<!-- Tab content -->
<div id="Movement" class="tabcontent">
  <h2>Movement</h2>
  <table>
    <tr>
        <td><img src="/demos/kart_racer_v_0_0_7_driving_on_wall.gif"/></td>
        <td><video preload="metadata" loop="loop" width="100%" height="512" controls >
  <source src="/wp-content/uploads/2019/07/smoothernow.mp4" type="video/mp4">
</video></td>
    </tr>
    <tr>
        <td>At the beginning of 2020 I spent several weeks prototyping some fun karting movement in Unity based on a technique described by <a href="https://twitter.com/kenneynl/status/1107783904784715788?lang=en">Kenney</a>. The results are super satisfying and I would really love to turn this into a Diddy Kong Racing-style racing adventure game one day, given the opportunity.</td>
        <td>Before I created the rolling ball motorcycle controller above, I experimented with using hover car physics, ie. adding upward forces to the motorcycle based on raycasts aimed at the ground. The results were pretty satisfying, but too bouncy for my tastes. Nevertheless I can see this being a fun, sci-fi style bike controller for a future project.</td>
    </tr>
    <tr>
        <td><img src="/demos/pointandclickmovement.gif"/></td>
        <td><img src="/wp-content/uploads/2019/07/thirdpersoncameracontroller.gif"/></td>
    </tr>
    <tr>
        <td>Using Unity's NavMesh, implementing a point and click system is fairly straightforward. The above demo benefits from Unity's new input system as well.</td>
        <td>I did this while trying to emulate the movement of the old Star Fox games. The movement itself is achieved my aiming the ship at a target with an offset ahead of the ship. There’s some artificial rolling there, too.</td>
    </tr>
  </table>

</div>

<div id="Cameras" class="tabcontent">
  <h2>Cameras</h2>

  <table>
    <tr>
        <td><img src="/wp-content/uploads/2020/09/cinemachineshowoff.gif"/></td>
        <td><video preload="metadata"  loop="loop" width="100%" height="512" controls >
  <source src="/wp-content/uploads/2019/07/smoothernow.mp4" type="video/mp4">
</video></td>
    </tr>
    <tr>
        <td>Cinemachine has made cameras a dream to work with. For this game I took inspiration from Grim Fandango's use of different camera angles for different rooms.</td>
        <td>Before Cinemachine was a possibility, I wanted to try out one of the techniques from <a href="https://youtu.be/C7307qRmlMI">this talk</a> regarding how you avoid obstacles in a third-person camera controller. I used raycast "whiskers" which detect incoming obstacles and move the camera to an optimal position to avoid them.</td>
    </tr>
  </table>

</div>

<div id="Dialogue" class="tabcontent">
  <h2>Dialogue</h2>

  <table>
    <tr>
        <td><video preload="metadata"  loop="loop" width="100%" height="512" controls >
  <source src="/demos/CaboozeDemoJanuaryMp4.mp4" type="video/mp4">
</video></td>
        <td><img src="/demos/insidetent.gif"/></td>
    </tr>
    <tr>
        <td>Ink is an excellent tool for implementing a dialogue system, and this demo hooks that up to Febucci's Text Animator.</td>
        <td>Yarnspinner is really quick to get working in Unity. I hooked it up to Febucci's Text Animator here.</td>
    </tr>
  </table>

</div>

<div id="UI" class="tabcontent">
  <h2>UI</h2>

  <table>
    <tr>
        <td><img src="/demos/messageswithyarnspinner3.gif"/></td>
        <td><img src="/wp-content/uploads/2019/07/fakephonewithcamera.gif"/></td>
    </tr>
    <tr>
        <td>UI in Unity has always been a struggle for me, so I decided to go all in on a complex demo. The text is supplied by Yarnspinner. The message bubbles are positioned manually every update. Perhaps the hardest part of this project was sizing the text bubbles dynamically, which involves some strange interactions between components and children in Unity.</td>
        <td>This was another, earlier attempt to learn UI in Unity, and I think the results speak for themselves. All of this is built with the standard Unity UI and a render texture; the phone’s clock comes from the System time.</td>
    </tr>
  </table>

</div>

<div id="Post-processing" class="tabcontent">
  <h2>Post-processing</h2>

  <table>
    <tr>
        <td><video preload="metadata"  loop="loop" width="100%" height="512" controls><source src="/demos/CaboozeClipSmoothPP.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
        <td>I wanted to have four separate times of day for Cabooze, and I achieved this with lighting, a custom skybox, and post-processing effects. Switching between them was jarring, though, so I used DOTween to interpolate each of the post-processing effects for a smooth transition.</td>
    </tr>
  </table>
</div>

<div id="Software-development" class="tabcontent">
  <h2>Software-development</h2>

  <table>
    <tr>
      <td><a href="http://www.youtube.com/watch?feature=player_embedded&v=b8h-r0bhitY
" target="_blank"><img src="http://img.youtube.com/vi/b8h-r0bhitY/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="240" height="180" border="10" /></a></td>
      <td><video preload="metadata"  loop="loop" width="100%" height="512" controls><source src="/demos/manageoperationallayers.mp4" type="video/mp4"></video></td>
    </tr>
    <tr>
      <td>
      My dissertation project was well documented, and you can find dev logs for it <a href="https://hudsonmiears.com/blog/">on my blog</a>. On the Unity side of things, the challenge was to develop an AR experience that keeps objects consistently in the same place in a small environment. 

      The project as a whole focused on UX design and phenomenology. As I move into the future, I'm certainly interested in pursuing these ideas further and in different directions!
      </td>
      <td>
      For the first six months at my current job, I worked on the ArcGIS Runtime SDK for Android Samples team. Many of the Kotlin samples were written by me. A challenge on this team was writing samples that were minimalistic and didn't include too much non-ArcGIS code, while also keeping UI intuitive and straightforward to use. I introduced some new techniques from Material design for this, such as the morphing FAB and bottom sheets, as well as some Kotlin-y techniques for front-loading the samples with ArcGIS code. I'm particularly proud of these samples: <a href="https://github.com/Esri/arcgis-runtime-samples-android/tree/master/kotlin/manage-operational-layers">1</a>, <a href="https://github.com/Esri/arcgis-runtime-samples-android/tree/master/kotlin/find-route">2</a>, and <a href="https://github.com/Esri/arcgis-runtime-samples-android/tree/master/kotlin/group-layers">3</a>.
      </td>
    </tr>
    <tr>
      <td><i>Unfortunately, I'm not allowed to show footage for this one!</i></td>
    </tr>
    <tr>
      <td>
      More recently in my current position I am working in C++ on some new features for the ArcGIS Runtime SDK. I'm super excited to be implementing functionality that helps users understand the world spatially!
      </td>
    </tr>
  </table>
</div>