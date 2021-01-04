---
id: 205
title: Reflecting on UX Design
date: 2019-10-07T14:43:09+00:00
author: hudsonmiears
layout: revision
guid: https://hudsonmiears.com/2019/10/07/185-revision-v1/
permalink: /2019/10/07/185-revision-v1/
---
<p class="has-drop-cap">
  I turned in my dissertation almost two months ago. Normally, a big project like this can be draining, and two months later the research, topic, and content can all feel stale and tired. It's curious to me, then, that the topics I explored in my Master's project&#8212;embedding information in the world, using a phenomenological lens to understand user experience&#8212;still seem to me like a vast and relatively unexplored world ripe for experimentation.
</p>

A key concept reaches out to me from all that research, and I can't get it out of my head. It was introduced to me from Tim Ingold's The Perception of the Environment: roughly, that we are incorporated in the environment and the environment within us in what he calls _enfoldment_; and beyond that: that we grow to understand the world and its information via the _unfolding_ of the environment around us. 

The _unfolding_ is the key, to me: if you imagine yourself as a tourist in a new city, how do you come to understand it and learn about it?

For some, especially those with a traditional academic background, I think, the answer may be to go to a history museum, or open an article on Wikipedia, and read the infodump of history and curiosities that have been curated for us. _This is what Reykjavik is. You should know [that it was established in AD 870 by Ingólfr Arnarson](https://en.wikipedia.org/wiki/Reykjav%C3%ADk#History), and that [alcohol is expensive at bars](https://en.wikipedia.org/wiki/Reykjav%C3%ADk#Nightlife)._<figure class="wp-block-image">

<img src="https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190106_142927-1024x768.jpg" alt="" class="wp-image-187" srcset="https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190106_142927-1024x768.jpg 1024w, https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190106_142927-300x225.jpg 300w, https://hudsonmiears.com/wp-content/uploads/2019/10/IMG_20190106_142927-768x576.jpg 768w" sizes="(max-width: 1024px) 100vw, 1024px" /> <figcaption>By and large, this is how the city looks in January.</figcaption></figure> 

That's a fine way to experience a city! But there is another method of travelling Reykjavik: leave your AirBnB, turn right at the end of the alley, and find an [interesting place to eat](https://g.page/icelandicstreetfood?share). Nearby you will see a [statue on a hill](https://goo.gl/maps/p5g6wvtasxLXA5XL8), but you're too close to the sea to stand for too long in the icy wind, and anyway you need only know that the man was important enough to have a statue downtown.

I'm a bit biased towards the latter; that was always my favorite way of being a tourist. Saunter down the city streets and pick out the thing that seems most interesting in the moment. Bit by bit, the culture starts to come alive: you piece together how much the city relies on tourism, how old it is and how the ancient culture informs the modern citizen, how important the church is and how its architecture reflects the native landscape's power over the mind.

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

When you're drawing a scene, you want objects to look three dimensional. One of the most important components to making objects look three dimensional is to simulate lighting in a way that is realistic. You do this by figuring out where the light is coming from, where the object is relative to the light, and how the light will affect the value of the object's surface.<figure class="wp-block-image">

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

I'm not giving this example to pick on Unity, but to highlight the difficulty of delivering tutorials in our current technological framework. That is, how do you teach someone how to make a toon shader? Your tools online are often limited to text and video. You have to get a lot of views to appear at the top of the Google search, so your video can't be too long and has to guarantee results. And I don't know if you've noticed, but tutorial series have a dramatic viewership dropoff after the first video.

#### Information and Knowledge

A key idea from my dissertation, which I drew from Tim Ingold's and David Abram's accounts of Australian Aboriginal cultures and the Koyukon tribe in Alaska, is the idea of information being embedded in the environment. Ingold focuses specifically on the process of an older mentor walking through the environment with a younger mentee. The mentor points to things, such as nearby plants, and names them, perhaps describing its qualities.

As I understand Ingold's writing, this is the extent of the mentor's role: to draw the attention of the mentee to important aspects of the environment. As the mentee focuses their attention on these things, and learns the bare facts and names, they begin to put together an understanding of how each actor in the environment works with all other actors. The system becomes known to the mentee by learning its components.

How dramatically different this is from the process of learning how to write a Toon Shader! In my own project, in which the nominal goal of the application itself was to teach users about the garden, I tried my best to ensure that tidbits of information were kept on this factual, observational level. I found that the users I tested walked away with a better understanding of the garden. I'm very curious today whether that information stuck with them.

#### How Games Teach Things

Gamification is a hot topic in the cybersphere (there's a sentence that would not have made sense 50 years ago). If you check the [Wikipedia article on Gamification](https://en.wikipedia.org/wiki/Gamification#Game_design_elements), you'll find it has quite a narrow definition of what it means to gamify an experience: points, leaderboards, narratives.

My own experience with game development and design, however, highlights how minimal these elements can be to the design of a game. Aren't achievements and leaderboards something you kind of tack on to the end of a fully fledged game?

The more interesting lesson we can learn from games, I think, is how they construct tutorials. Or in some cases, how they don't construct a tutorial at all. I want to take a look at both approaches here, because I think they go hand in hand.

I've linked this video before on this blog, but I'm going to link it again because it describes a design philosophy for creating game tutorials that, in my experience, is quite pervasive in the greater conversation about this topic.<figure class="wp-block-embed-youtube wp-block-embed is-type-video is-provider-youtube wp-embed-aspect-16-9 wp-has-aspect-ratio">

<div class="wp-block-embed__wrapper">
</div><figcaption>I highly recommend watching the whole thing; Mark Brown makes great videos.</figcaption></figure> 

Mark Brown here is specifically talking about Super Mario 3D World's approach to teaching players new mechanics:

  1. The player is introduced to the mechanic in a safe space.
  2. The player is given room to explore and develop their understanding of the mechanic.
  3. The level throws the player a twist, turning the mechanic on its head and testing the player on their understanding.
  4. The player is given a space to show off their understanding.

The core of this is the idea that players learn how to play the game in a way that feels organic&#8212;they make the decisions, they are not told directly what to do, they can screw up as often as they please&#8212;but the level is designed in such a way as to push the player along a predetermined path which, while leaving the player some space to experiment and innovate, will basically ensure that the player does exactly what the designer intends.

I don't think this is a novel concept in UX design, though, with talk of affordances and breadcrumbs and other related concepts. It's a common and generalizable idea to organically push a user towards some intended method of using a software or exploring an experience.

Instead, let's look at an entirely different game with an entirely different style of tutorial: Minecraft.

Minecraft is most commonly called a &#8216;sandbox' game, evoking the idea of a child playing in a sandbox. There are no rules or limitations on how the player engages with the game (in fact, this goes beyond the game itself&#8212;the culture around Minecraft is very much to install modifications to the game created by other players to add new content or visuals). The only rules to Minecraft are the systemic rules embedded in the game's code. By nature, the environment is procedurally generated (so there's no level designer) and the player can destroy and reshape all of it (so in fact, the player is the designer).

So how does Minecraft teach the player how to play? I think, in the latest version, there's a bit of a text tutorial, but I'll speak more about how the game was experienced at the start of its popularity several years ago. 

The player is dropped into a world with no information at all. They can move with the WASD keys and look around by moving the mouse; the left mouse button is used to destroy blocks and the right mouse button is used to place blocks or interact with things. Of course, the player is not told these things. Instead, the player has to rely on a bit of past knowledge (the movement with WASD + Mouse is quite standard in games) and just play around. Undoubtedly, they will press the left mouse button on the bit of sand or dirt they're standing on and see that it starts to break. They'll see that they pick up the block and can place it down with a right click. Eventually, they will start to destroy a tree, notice the crafting interface in their inventory, and learn how to create planks of wood.

It is entirely organic. Well, not entirely&#8212;a core part of the Minecraft experience has always been in consuming tutorials and let's play videos on the internet, or googling crafting recipes&#8212;but ignoring that, the game gives you all the tools to learn without teaching you how to use them.

What's interesting about games is that they have to teach you _some_ things, like how to interface with them, but they can't teach you _everything_, because by their very nature players must learn how the game works on their own. If the game tells you how to defeat the final boss or get the highest score, often times that would kill the experience for the player.

Coming back to Minecraft's secondary experience, that of online tutorials and videos made by the community: I think that this works for the game because of its lack of clearly defined goals (at least, when the game was first released). Someone can tell you how to build your first tools, but they can't tell you how to beat the game, because each individual player creates their own goals and, by proxy, their own intended style of play.

One final point to make about Minecraft (to be fair, it is one of the most popular games of all time, and so it is an endless source of information). As players learn how to play the game, they will learn how to craft new items. And as they learn to craft new items, they will place those items in the world. The world they create is therefore a perfect measure of their skill level and progress through the game, even if there is no clearly defined direction of progress. This is a huge boon to Minecraft and other sandbox games.

#### How does this relate to applications, education, and AR?

Am I suggesting that the ideal method of teaching is the sandbox? Not quite. But I would like to pose a question:

How did you learn how to use MS Paint?<figure class="wp-block-image">

![](https://icdn7.digitaltrends.com/image/ms-paint-windows-95-header-768x768.jpg) <figcaption>[Thanks Digital Trends](https://www.digitaltrends.com/computing/why-people-still-love-ms-paint/).</figcaption></figure> 

If you're like me, and you learned it quite young and primarily as a digital toy, then you learned how to use MS Paint by doodling on the screen with your mouse and playing with all the different options.