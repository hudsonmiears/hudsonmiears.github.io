---
id: 113
title: 'ARCore and Unity Dev Log: Introduction'
date: 2019-05-28T10:29:11+00:00
author: hudsonmiears
excerpt: "This post explains the foundation on which I'm building my master's thesis project, an ARCore app using Unity3D with a novel method of analysing UX."
layout: revision
guid: https://hudsonmiears.com/2019/05/28/110-revision-v1/
permalink: /2019/05/28/110-revision-v1/
---
I was afraid of AR. Honestly&#8212;it seems like the last thing we need is another reason to cover up the real world with digital messages, advertisements, and games. It&#8217;s a slippery slope!

So naturally, I&#8217;m using it for my Master&#8217;s thesis.

In my last semester of this degree I took a UX design course, and in it we were introduced to [The Lion&#8217;s Gate](http://blogs.napier.ac.uk/thelionsgate/), a design project at Edinburgh Napier which aims to merge the natural and digital worlds. It draws a lot on permaculture, and through this project I&#8217;ve become obsessed with permaculture&#8212;but that&#8217;s not the focus here.

A few months ago I ran into the man behind the project on the bus, and together we developed a dissertation idea which would utilise mobile AR in the gardens in an attempt to enhance the natural space rather than detract from it.

So how can we use UX design to implement a healthy AR experience?

I&#8217;ve only had the one UX course, so I delved into some literature to figure out how to adequately test an app for user experience. The key consideration here was that the garden is a real-world, three-dimensional space, and we want to ensure that users feel that they are in a garden rather than staring at their phones.

The literature I looked at initially were all museum studies. Museum studies seem like a great resource to pull from here&#8212;in a sense, The Lion&#8217;s Gate is a museum, and one of my supervisor&#8217;s ideas was to create a virtual guided tour of the space using AR. The standout article to me was a paper by Pallud and Monod (2010) called _[User experience of museum technologies: the phenomenological scales](https://www.researchgate.net/publication/45064223_User_experience_of_museum_technologies_The_phenomenological_scales)_. 

The interest in this paper stems from their method of analysis. Pallud and Monod used a framework for analysis using the philosophy of phenomenology. The researchers examined how visitors of museums reacted to museum technologies, focussing on how the visitors could project themselves into the historical characters being presented or envision the events being referenced.

The framework itself comes from [Monod and Klein (2005)](https://www.researchgate.net/publication/220891459_A_Phenomenological_Evaluation_Framework_for_Cultural_Heritage_Interpretation_From_e-HS_to_Heidegger%27s_Historicity), and it&#8217;s based on phenomenological philosophy. I had never been exposed to using philosophy as a means to examine the effectiveness of a new technology, and with some effort I was able to understand some of the basic concepts of phenomenology.

To keep this relatively short, though, I won&#8217;t describe phenomenology. It is a complex and unfamiliar philosophy, and I started to question whether I was doing a computer science degree after all.

After discussing this study with my supervisor, he led me to eco-phenomenology, an offshoot of phenomenology spearheaded by Merleau-Ponty. Where phenomenology examines time, space, and perception, eco-phenomenology relates these ideas back to the real-world.

To present an idea of what eco-phenomenology can be like, I&#8217;ll quote David Abram in his book _The Spell of the Sensuous_:

<blockquote class="wp-block-quote">
  <p>
    <br />&#8220;The human body with its various predilections is, to be sure, our <em>own</em> inheritance, our own rootedness in an evolutionary history and a particular ancestry. Yet it is also our insertion in a world that exceeds our grasp in every direction, our means of contact with things and lives that are still unfolding, open and indeterminate, all around us. Indeed, from the perspective of my bodily senses, there is no thing that appears as a completely determinate or finished object. Each thing, each entity that my body sees, presents some face or facet of itself to my gaze while withholding other aspects from view.&#8221;
  </p>
  
  <cite><em>The Spell of the Sensuous</em>, p. 50<br /></cite>
</blockquote>

Here in eco-phenomenology I had discovered an incredible way to analyze an AR app about nature: referencing the framework from Monod and Klein (2005) and modifying it to fit eco-phenomenological principles rather than phenomenological ones, I could examine how the AR experience enhanced users&#8217; connection to nature.

This still ignores a final aspect of The Lion&#8217;s Gate, that being permaculture. Permaculture is a method of agriculture created by Bill Mollison. The central idea behind it is to mimick natural systems, especially the forest, but modify the plants within that natural system to ensure that humans are fed. That&#8217;s a simplistic description missing a lot of the nuance, but it gets the idea across. [The Lion&#8217;s Gate is built on top of a merger between UX design principles and permaculture principles](https://ewic.bcs.org/upload/pdf/ewic_hci17_sp_paper20.pdf). 

One of the most interesting aspects of permaculture is in Bill Mollison&#8217;s hefty textbook, _The Permaculture Designer&#8217;s Manual_. Chapter 4 of the book is dedicated to &#8220;Pattern Understanding&#8221;, by which Mollison is referring to the natural patterns found repeated throughout nature. Examples include the torus, the spiral, branches, amongst many others. Surely in a design methodology including permaculture this pattern understanding must be referred to.

Tying all of these thoughts together is difficult, but it has led to a general idea that looks like this:

  1. The project will consist of two parts: an AR app and a method of analysis.
  2. The app will employ principles from HCI, UX Design, and permaculture.
  3. The app should enhance users&#8217; sense of place in nature.
  4. The app should be analysed with questionnaires and semi-structured interviews to answer whether 3. has been achieved effectively.
  5. The questions in 4. will be based on Monod and Klein&#8217;s (2005) framework for phenomenological analysis, modified to best fit eco-phenomenological principles.

With all that said, it was time to get started.