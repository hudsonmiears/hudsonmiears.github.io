---
id: 197
title: Information in the Information Age
date: 2019-10-04T12:44:44+00:00
author: hudsonmiears
layout: revision
guid: https://hudsonmiears.com/2019/10/04/185-revision-v1/
permalink: /2019/10/04/185-revision-v1/
---
<p class="has-drop-cap">
  I turned in my dissertation almost two months ago. Normally, a big project like this can be draining, and two months later the research, topic, and content can all feel stale and tired. It&#8217;s curious to me, then, that the topics I explored in my Master&#8217;s project&#8212;embedding information in the world, using a phenomenological lens to understand user experience&#8212;still seem to me like a vast and relatively unexplored world ripe for experimentation.
</p>

A key concept reaches out to me from all that research, and I can&#8217;t get it out of my head. It was introduced to me from Tim Ingold&#8217;s The Perception of the Environment: roughly, that we are incorporated in the environment and the environment within us in what he calls _enfoldment_; and beyond that: that we grow to understand the world and its information via the _unfolding_ of the environment around us. 

The _unfolding_ is the key, to me: if you imagine yourself as a tourist in a new city, how do you come to understand it and learn about it?

For some, especially those with a traditional academic background, I think, the answer may be to go to a history museum, or open an article on Wikipedia, and read the infodump of history and curiosities that have been curated for us. _This is what Reykjavik is. You should know [that it was established in AD 870 by Ingólfr Arnarson](https://en.wikipedia.org/wiki/Reykjav%C3%ADk#History), and that [alcohol is expensive at bars](https://en.wikipedia.org/wiki/Reykjav%C3%ADk#Nightlife)._<figure class="wp-block-image">

<img src="https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190106_142927-1024x768.jpg" alt="" class="wp-image-187" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190106_142927-1024x768.jpg 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190106_142927-300x225.jpg 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190106_142927-768x576.jpg 768w" sizes="(max-width: 1024px) 100vw, 1024px" /> <figcaption>By and large, this is how the city looks in January.</figcaption></figure> 

That&#8217;s a fine way to experience a city! But there is another method of travelling Reykjavik: leave your AirBnB, turn right at the end of the alley, and find an [interesting place to eat](https://g.page/icelandicstreetfood?share). Nearby you will see a [statue on a hill](https://goo.gl/maps/p5g6wvtasxLXA5XL8), but you&#8217;re too close to the sea to stand for too long in the icy wind, and anyway you need only know that the man was important enough to have a statue downtown.

I&#8217;m a bit biased towards the latter; that was always my favorite way of being a tourist. Saunter down the city streets and pick out the thing that seems most interesting in the moment. Bit by bit, the culture starts to come alive: you piece together how much the city relies on tourism, how old it is and how the ancient culture informs the modern citizen, how important the church is and how its architecture reflects the native landscape&#8217;s power over the mind.

<ul class="wp-block-gallery columns-2 is-cropped">
  <li class="blocks-gallery-item">
    <figure><img src="https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190104_151805-1024x768.jpg" alt="" data-id="188" data-link="https://hudsonmiears.com/?attachment_id=188" class="wp-image-188" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190104_151805-1024x768.jpg 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190104_151805-300x225.jpg 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190104_151805-768x576.jpg 768w" sizes="(max-width: 1024px) 100vw, 1024px" /></figure>
  </li>
  <li class="blocks-gallery-item">
    <figure><img src="https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190104_140805-1024x768.jpg" alt="" data-id="189" data-link="https://hudsonmiears.com/?attachment_id=189" class="wp-image-189" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190104_140805-1024x768.jpg 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190104_140805-300x225.jpg 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190104_140805-768x576.jpg 768w" sizes="(max-width: 1024px) 100vw, 1024px" /></figure>
  </li>
</ul>

It is a process that _feels_ like information unfolding before you, exactly as Tim Ingold describes, or perhaps exactly as I interpreted his description, vaguely through the shear of misremembered thoughts and interwoven with the research I was doing at the time.

If you can bear with me and agree that this is a great way to be a tourist, then come down the rabbit hole with me as I relate this to the information age.

#### How to write a toon shader for Unity3D

(As I said, bear with me.)

When you&#8217;re drawing a scene, you want objects to look three dimensional. One of the most important components to making objects look three dimensional is to simulate lighting in a way that is realistic. You do this by figuring out where the light is coming from, where the object is relative to the light, and how the light will affect the value of the object&#8217;s surface.<figure class="wp-block-image">

![](https://thevirtualinstructor.com/images/lightsourcebulb.jpg) <figcaption>[Thank you Matt Fussel.](https://thevirtualinstructor.com/shading-techniques-basics.html)</figcaption></figure> 

This is great for traditional art forms, but in animated cartoons, time is of the essence, and rendering complex lighting like this frame by frame would be prohibitively expensive. Instead, objects are divided into light and dark sections; the shadow is drawn with no gradients.<figure class="wp-block-image is-resized">

<img src="https://vignette.wikia.nocookie.net/avatar/images/0/06/Rock_on_slope.png/revision/latest?cb=20140403224713" alt="" width="566" height="425" /> <figcaption>[Thank you Avatar Wiki](https://avatar.fandom.com/wiki/Bitter_Work). Note: Focus on the boulder here: the background would have been more static and thus used for multiple frames, so animators can afford to spend more time on shading here. The boulder is animated, so it gets the simple treatment.</figcaption></figure> 

One of the great things about 3D animation, like that used in games, is that the lighting is calculated by the computer. Environment artists decide where to place the lights in the environment, and then every frame (1/60th of a second), the computer calculates how to shade the object. Programmers decide _how_ the computer calculates the shading by writing programs called shaders. Some games aim for a hyperrealistic look; others have tried to emulate the nostalgic feel of cartoons with a _toon shader_.

<ul class="wp-block-gallery columns-2 is-cropped">
  <li class="blocks-gallery-item">
    <figure><img src="https://hudsonmiears.com/wp-content/uploads/2019/10/the-order-1886-environment-sc003-1024x576.jpg" alt="" data-id="191" data-link="https://hudsonmiears.com/?attachment_id=191" class="wp-image-191" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/the-order-1886-environment-sc003-1024x576.jpg 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/the-order-1886-environment-sc003-300x169.jpg 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/the-order-1886-environment-sc003-768x432.jpg 768w, https://hudsonmiears.com/wp-content/uploads/2019/10/the-order-1886-environment-sc003.jpg 1280w" sizes="(max-width: 1024px) 100vw, 1024px" /><figcaption><a href="https://www.playstation.com/en-gb/games/the-order-1886-ps4/environment/">The Order: 1886</a></figcaption></figure>
  </li>
  <li class="blocks-gallery-item">
    <figure><img src="https://hudsonmiears.com/wp-content/uploads/2019/10/botw-1024x569.png" alt="" data-id="192" data-link="https://hudsonmiears.com/?attachment_id=192" class="wp-image-192" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/botw-1024x569.png 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/botw-300x167.png 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/botw-768x427.png 768w, https://hudsonmiears.com/wp-content/uploads/2019/10/botw.png 1222w" sizes="(max-width: 1024px) 100vw, 1024px" /><figcaption><a href="https://www.zelda.com/breath-of-the-wild/media">The Legend of Zelda: Breath of the Wild</a></figcaption></figure>
  </li>
</ul>

By default, Unity3D leans towards the realistic end of the shader spectrum. So how do you make a toon shader in Unity?

<ul class="wp-block-gallery columns-1 is-cropped">
  <li class="blocks-gallery-item">
    <figure><img src="https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadersearch-1024x540.png" alt="" data-id="193" data-link="https://hudsonmiears.com/?attachment_id=193" class="wp-image-193" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadersearch-1024x540.png 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadersearch-300x158.png 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadersearch-768x405.png 768w" sizes="(max-width: 1024px) 100vw, 1024px" /><figcaption>1. Search on Google. You will be inundated with search results.</figcaption></figure>
  </li>
  <li class="blocks-gallery-item">
    <figure><img src="https://hudsonmiears.com/wp-content/uploads/2019/10/toonshaderopenvieo-1024x487.png" alt="" data-id="194" data-link="https://hudsonmiears.com/?attachment_id=194" class="wp-image-194" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/toonshaderopenvieo-1024x487.png 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/toonshaderopenvieo-300x143.png 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/toonshaderopenvieo-768x366.png 768w" sizes="(max-width: 1024px) 100vw, 1024px" /><figcaption>2. Choose a video that looks like it will give you an answer.</figcaption></figure>
  </li>
  <li class="blocks-gallery-item">
    <figure><img src="https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadersplash-1024x482.png" alt="" data-id="195" data-link="https://hudsonmiears.com/?attachment_id=195" class="wp-image-195" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadersplash-1024x482.png 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadersplash-300x141.png 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadersplash-768x361.png 768w" sizes="(max-width: 1024px) 100vw, 1024px" /><figcaption>3. The video presents you with the entire shader all at once, and walks through each part of the shader program.</figcaption></figure>
  </li>
  <li class="blocks-gallery-item">
    <figure><img src="https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadercomment-1024x249.png" alt="" data-id="196" data-link="https://hudsonmiears.com/?attachment_id=196" class="wp-image-196" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadercomment-1024x249.png 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadercomment-300x73.png 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadercomment-768x187.png 768w, https://hudsonmiears.com/wp-content/uploads/2019/10/toonshadercomment.png 1177w" sizes="(max-width: 1024px) 100vw, 1024px" /><figcaption>4. This comment sums up many of the other comments on the video.</figcaption></figure>
  </li>
</ul>

I&#8217;m not giving this example to pick on Unity, but to highlight the difficulty of delivering tutorials in our current technological framework. That is, how do you teach someone how to make a toon shader? Your tools online are often limited to text and video. You have to get a lot of views to appear at the top of the Google search, so your video can&#8217;t be too long and has to guarantee results.