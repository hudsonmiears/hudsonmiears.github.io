---
id: 148
title: Augmented Reality and The Lifeworld (dev log week 5)
date: 2019-06-28T09:13:59+00:00
author: hudsonmiears
excerpt: I approached this topic coming from the perspective of "I want to design a meaningful AR experience", but it quickly led me into a wealth of literature that touches on what a meaningful AR experience actually means.
layout: revision
guid: https://hudsonmiears.com/2019/06/28/136-revision-v1/
permalink: /2019/06/28/136-revision-v1/
---
I don't have much in the way of tangible progress for the week as I've been focussed on research and writing, so in lieu of a dev log, I wanted to ramble a bit about the topic of blended spaces, phenomenology, and augmented reality. Essentially, exactly the research that I've been doing&#8212;but with less of the formality of the literature review that I'll be completing this week.

<p class="has-small-font-size">
  <em>Note: I'm using the term AR here mostly to refer to mobile augmented reality, ie. technology that overlays digital information on a camera feed, as with ARCore, ARKit, Vuforia, etc.</em>
</p>

I approached this topic coming from the perspective of &#8220;I want to design a meaningful AR experience&#8221;, but it quickly led me into a wealth of literature that touches on what a meaningful AR experience actually means. The project at hand already had a background in David Benyon's writings on blended spaces, but I was as yet unaware of the philosophical grounding behind the theory.

In an [old essay about games](https://hudsonmiears.com/2018/06/04/mimesis-and-mechanics-as-narration/) (in which I was woefully unaware of terminology or any real academic theory on interaction design), I talked about video games' unique ability for empathy, in that interaction allows players to relate to characters on the screen in a way that is more real than say, a book or a movie allows. 

But games still have an innate separation between the user and the character. No matter how well the user is able to empathize with the character, there is a very real barrier (ie., the screen, the game world, the controller) between the two. As I'm working through the literature on blended spaces, I come across the idea of presence: the feeling of being amongst the action, there in whatever environment is relevant to the task at hand<span id='easy-footnote-1-148' class='easy-footnote-margin-adjust'></span><span class='easy-footnote'><a href='https://hudsonmiears.com/2019/06/28/136-revision-v1/#easy-footnote-bottom-1-148' title='See Benyon's &#8220;Spaces of Interaction, Places for Experience&#8221; chapter 2.2.1.'><sup>1</sup></a></span>. Presence is certainly a factor in games&#8212;we talk often about immersion&#8212;but can that barrier ever truly disappear?

It certainly seems to the first time you experience _virtual_ reality. You put on the headset and boot up SUPERHOT, and the room you're in disappears; the people you're with disappear. Even the controller in your hand disappears as soon as you get used to the inputs. A low-poly avatar raises its arm and a sleek gun flashes. You duck instinctively; the bullet passes over your head, and as you crouch low, you notice the leg of a second avatar stepping toward you. It's thirty minutes later and you realize that you've left your friend in meatspace while you play out a Jackie Chan fight scene.

But that's _virtual_ reality, and though the technology is similar, the community is similar, and we group the two together with the hashtag #XR, _augmented_ reality seems to me to offer a quite different experience.

You pull out your phone and open [Brickscape](https://play.google.com/store/apps/details?id=com.fiveminlab.brickscape&hl=en_US), a three-dimensional puzzle much like [Rush Hour](https://www.thinkfun.com/products/rush-hour/), and turn on the AR mode. The cubist conundrum settles on the pavement in front of you, and you can walk your real, human body around it to get a different angle. It's fun, but you can also sit in place and rotate the cube with your fingers on the phone screen. After a while, you turn off the AR mode; no sense having the camera on while it drains your battery.

Next you download [Just a Line](https://play.google.com/store/apps/details?id=com.arexperiments.justaline), a Google-made snippet that lets you draw lines around your living room. You walk aimlessly around your house, writing notes on the kitchen counter or making a really, really long snake that slithers from room to room. You get a kick out of recording a video: the camera looks at a blank wall, then turns around to reveal a handdrawn sign directing you to the next room<span id='easy-footnote-2-148' class='easy-footnote-margin-adjust'></span><span class='easy-footnote'><a href='https://hudsonmiears.com/2019/06/28/136-revision-v1/#easy-footnote-bottom-2-148' title='I admit that I recorded more videos than my friends appreciated.'><sup>2</sup></a></span>. The experience is a bit more tangible than Brickscape; at the very least, the digital creations are tied to real-world locations.

But there's an itch that's waiting to be scratched. You try [ARrrrrgh](https://play.google.com/store/apps/details?id=com.warpinmedia.arrrrrgh): you hide a treasure chest under a cherry tree, then hand the phone off to your friend a few meters away. With excitement, you tell them to find the treasure. They find it; there's little reward. Yet despite the uninspiring finish, there's some satisfaction to it: the tree was a landmark. It makes sense to hide treasure there.

There's still something missing, though.

For me, the question of a meaningful AR experience tied into the unique feature that AR presents: the real world. With the magic of image recognition and on-device cameras, digital creations can become real. They can become things that you interact with as you move your real body; you can see them against a real background, and if you move your eyes off the screen, you can see the same background there in the world.

So why don't the apps I've mentioned above hit the mark? They do exactly that: they place a digital object on a real background. Why don't the puzzle and the drawings feel like they exist in the real world? What's missing from ARrrrrgh?

I'm just off reading quite a bit of Paul Dourish's _[Where the Action Is](http://www.dourish.com/embodied/)._ It is a fascinating read so far and extremely relevant to current technologies. On page 38, he defines augmented reality:

<blockquote class="wp-block-quote">
  <p>
    &#8220;The ubiquitous computing approach to interaction&#8212;what Weiser dubbed &#8216;physical virtuality' and would become known as augmented reality&#8212;does just the opposite [from virtual reality]. It moves the computer into the real world. The site of interaction is the world of the user, not that of the system. That world, in the agumented reality vision, may be imbued with computation, but the computer itself takes a back seat.&#8221;
  </p>
  
  <cite><em>Where the Action Is</em>, Paul Dourish, ch. 2 p. 38.</cite>
</blockquote>

And he goes on to distinguish between virtual and augmented reality even further in a later chapter:

<blockquote class="wp-block-quote">
  <p>
    &#8220;Even in an immersive virtual-reality environment, users are disconnected observers of a world they do not inhabit directly. They peer out at it, figure out what's going on, decide on some course of action, and enact it through the narrow interface of the keyboard or the data-glove, carefully monitoring the result to see if it turns out the way they expected. Our experience in the everyday world is not of that sort. There is no homunculus sitting inside out heads, staring out at the world through our eyes, enacting some plan of action by manipulating our hands, and checking carefully to make sure we don't overshoot when reaching for the coffee cup. We inhabit our bodies and they in turn inhabit the world, with seamless connections back and forth.&#8221;
  </p>
  
  <cite><em>Where the Action Is,</em> Paul Dourish, ch.4 p. 102.</cite>
</blockquote>

We're getting somewhere, now. As predicted, the world is the key to augmented reality. But why is the world important? I take yet another quote from Paul Dourish:

<blockquote class="wp-block-quote">
  <p>
    &#8220;We find the world meaningful primarily with respect to the ways in which we act within it.&#8221;
  </p>
  
  <cite><em>Where the Action Is</em>, Paul Dourish, ch.4 p. 125</cite>
</blockquote>

I would very much like to give full context to this answer, but doing so would require an entire book, and that book has already been written by Paul Dourish.

So we know that the world is an important factor, but why is that so? How do we use that effectively?

David Abram in his book _The Spell of the Sensuous_ draws upon the philosophies of Lucien Lévy-Bruhl and Maurice Merleau-Ponty in describing &#8220;the participatory nature of perception&#8221;. The idea is that perceiving the world is an active experience; while our perception is directly mediated by the senses, we are constantly projecting those senses beyond what we directly perceive. Abram gives the example of a sleight-of-hand magic trick:

<blockquote class="wp-block-quote">
  <p>
    &#8220;The spectators' eyes, already drawn by the coin's fluid dance across the magician's fingers, sponta­neously fill in those gaps with impossible events, and it is this spon­taneous involvement of the spectators' own senses that enables the coin to vanish and reappear, or to pass through the magician's hand.&#8221;
  </p>
  
  <cite><em>The Spell of the Sensuous, </em>David Abram, ch.2 p. 56.</cite>
</blockquote>

The idea here is that when we are interacting with the real world, we are constantly engaging our senses with what we perceive and what we don't perceive, permitting those inexplicable events some sensuous explanation.

So why is this limited to the real world, if it is indeed limited? Why don't I feel the same sense of awe as my character casts a spell in _Skyrim_ as I feel when a magician pulls my card out of a deck?

One possible explanation is that our experience of the real world incorporates the senses holistically, whilst digital experiences are limited to sight and sound. But I find that explanation wanting.

Perhaps we should return to that distinction between virtual reality and the real world that Dourish provided: in virtual reality we peer out at the world and make logical, planned decisions about the next course of action. In the real world, there is no such sequential planning; we are quite literally incorporated into the real world; we are present in it.

My thinking goes like this: In a virtual world, we can be present, but we are always looking through that bottleneck of the computer interface. Our sensuous imagination is enveloped entirely, unmediated (except by a narrow range of sight, sound, and the occasional vibration of the control) by real sense feedback. We are inhabiting a world devoted entirely to the &#8216;magic of the coin disappearing', and there is no grounding in the world itself. <span id='easy-footnote-3-148' class='easy-footnote-margin-adjust'></span><span class='easy-footnote'><a href='https://hudsonmiears.com/2019/06/28/136-revision-v1/#easy-footnote-bottom-3-148' title=' To be clear, I'm not disparaging games here. I love (non-AR) games and I think they have enormous capacity for meaningful experiences. I just want to draw a distinction. '><sup>3</sup></a></span>

The real world contrasts this. We are not bottlenecked at all. Even when our senses are focused, there are peripheral sensations. Our expectations are not in the magical. When the magical occurs, it is a surprise: we are engaged with a phenomenon that seems both real and unreal. Unreal because the sensation is inexplicable by what we normally experience, but real because we know that it is occuring in the real world, enveloped in the sensations that we associate with the real world.

Now we are left with the crucial question: how do we use this phenomenon to our advantage in augmented reality? Surely, when holding a mobile phone and looking through a camera feed, we are creating a bottleneck between our senses and the real world.

And indeed we find that that is the case. In the AR titles I mentioned above, I found that all but ARrrrrgh were failing in some quality of real experience. They utilize the real world to some degree, but they lack the grounding in the real world that allows us to experience _magic_.

In order to create that magic, the experience must play on our expectations. It must use the real world as a grounding force, incorporating the senses, providing little barrier between what is real and what is on the screen. Then, when our expectations are settled, we can guide the user from their real expectations to a new phenomenon, one that uses the senses already engaged to &#8220;spontaneously fill in those gaps with impossible events&#8221;.

Now we can return to my own project.

The Lion's Gate project is an attempt to blend the digital and ecological spaces on Edinburgh Napier University campus. It is a garden, and the garden is based on permaculture principles; indeed, most if not all of the design considerations for the project have their roots in a blend of permaculture and user experience.

Permaculture, for the uninitiated, is an agricultural design philosophy. Its core tenets are to emulate systems found in nature in order to produce more efficient food-growing-systems for humans. Create a forest, but maximize the output, such that all trees are either fruit-producing or aid the production of other plants.

One key idea found in permaculture is in the layers of the food forest. When designing a forest, one should consider all of the layers of plants and animals that inhabit it: the canopy (tall trees) are at the top, below are slightly shorter trees, below that bushes, below that groundcover, below that are root crops and soil microbes, and through it all are climbing vines and other animals.

In The Lion's Gate project, digital information is envisioned as constituting an additional layer. Digital signals are constantly passing through all the layers of the forest in the form of internet or cell service. How do we pull that layer out into a tangible form, such that we can see how information interacts with the environment? Indeed, Bill Mollison claims that information is the most valuable yield that can be acquired from nature.

In Tim Ingold's book of essays _The Perception of the Environment_, he points to the Koyukon of northern Canada and the Aboriginal peoples of Australia. In both cultures, there is a system of passing on knowledge that is very similar (and prevalent in many others). Mentors walk with the mentored out in the world and direct the mentee's attention to various things: moss, fungi, a ladybug or a shrub. An observation is made about the thing. To Ingold, information exists in the world, just as Mollison said; knowledge is acquired by paying attention to the things within it. As the observer attends to elements of the environment, the elements join together to form new connections in the observer's mind, producing knowledge that can later be used.

Yet there are elements in the garden that are not easily attended to. Pollen sticks to a bee's legs and back, but we can't always see it. Mycorrhizal fungi inhabit the earth, some creating nitrogen nodules on leguminous plant roots, thus feeding the soil with essential nutrients to life. But to see these you must pull out the plant, killing it. To see the effect on other plants, you must wait for the soil to grow.

These are real processes, yet they are invisible to us, except in careful conditions, and then usually under a microscope. But we don't need to see them directly; we only need to perceive them, or as Abram has said, to participate in the perception of them. We only need our attention drawn to the processes, and then, as we attend to more of them, we will create knowledge from the information in the world.

The best way to do this, I think, is to show the magic in the processes. To ground the user's senses there in the garden, amongst the plants and creatures, where there expectations of ecology are fairly static. Then, using _magic_<span id='easy-footnote-4-148' class='easy-footnote-margin-adjust'></span><span class='easy-footnote'><a href='https://hudsonmiears.com/2019/06/28/136-revision-v1/#easy-footnote-bottom-4-148' title='By which I mean technology.'><sup>4</sup></a></span>, we can engage their senses (and therefore their attention) with the processes that can't be seen. We can ask the question&#8212;&#8220;how can two flowers on opposite sides of a plant bed mate with each other&#8221;&#8212;and then we can guide the user's attention to the necessary components and let them put the information together in their minds. Near the beehive, they are told about the action of the bees. Near the flower, they are told that pollen is essential to seed development. And in their imagination, they connect the two.

Augmented Reality, in this case, is a sort of microscope. It allows users to sense the invisible information layer and attend to the _magic_ processes of life. The education is up to them. Everything they are experiencing is grounded in the real world, because doing so permits a magical experience.

That's the theory of my dissertation project, and it's taken me quite a while to reach a point where the research has come together in a coherent way. There's a lot more to it, namely that I have to analyze and assess the experience of my creation, but this post is lengthy enough.

Finally, I don't think the theories I'm presenting here are unique to educational experiences either. There is an enormous range of possibilities in augmented reality, and I've only just dived into user experience with this project. There's so much to learn and so much to make.

This write-up composes a fairly good outline and basis for my actual, academic literature review, so any feedback is extremely useful; please let me know in the comments, via email, or on whatever platform you found this on.

Thanks for reading!