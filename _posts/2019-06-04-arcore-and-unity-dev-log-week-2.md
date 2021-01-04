---
id: 120
title: 'ARCore and Unity Dev Log: Week 2'
date: 2019-06-04T11:57:27+00:00
author: hudsonmiears
excerpt: In this post I review week 2 of my dissertation project on UX, ARCore, and Unity, with a focus on Tim Ingold and Firebase downloads.
layout: post
guid: https://hudsonmiears.com/?p=120
permalink: /2019/06/04/arcore-and-unity-dev-log-week-2/
image: /wp-content/uploads/2019/06/thoughts30to35-e1559649311878-920x575.jpg
categories:
  - Design
  - Dev Log
tags:
  - ar
  - arcore
  - design
  - dev-log
  - firebase
  - phenomenology
  - unity
  - ux
---
Welcome back! This post describes week 2 of my dissertation project. To find out more about the project itself, have a look at the [intro log](https://hudsonmiears.com/2019/05/28/arcore-and-unity-dev-log-introduction/).

This week saw a decrease in the amount of &#8216;tangible&#8217; progress, but throughout the week I think I started to really solidify the project aims, research foundation, and project plan.

Days 1 and 2 (28 and 29 May) were personal days for myself to work on my CV, write up the [intro](https://hudsonmiears.com/2019/05/28/arcore-and-unity-dev-log-introduction/) and [week 1](https://hudsonmiears.com/2019/05/28/arcore-and-unity-dev-log-week-1/) logs, and research job opportunities for the future.

#### 30/5/19

On Thursday I started reading Tim Ingold&#8217;s book &#8216;Perception of the Environment&#8217;. So far I&#8217;d recommend it to anyone even slightly interested in the topic. Tim Ingold is an anthropologist, and the book is a collection of essays which attempt to bring together two sides of anthropology: the side that describes everything according to scientific rules like natural selection, and the side that describes everything according to cultural constructs. That&#8217;s a huge simplification, so don&#8217;t take my word for it.

<div class="wp-block-image">
  <figure class="aligncenter is-resized"><img src="https://hudsonmiears.com/wp-content/uploads/2019/06/thoughts30to35-e1559649311878-768x1024.jpg" alt="" class="wp-image-121" width="384" height="512" srcset="https://hudsonmiears.com/wp-content/uploads/2019/06/thoughts30to35-e1559649311878-768x1024.jpg 768w, https://hudsonmiears.com/wp-content/uploads/2019/06/thoughts30to35-e1559649311878-225x300.jpg 225w" sizes="(max-width: 384px) 100vw, 384px" /><figcaption>My handwriting devolved as my pen scratched across the page at lightning speed.</figcaption></figure>
</div>

I&#8217;m finding this book very useful in consolidating a lot of the free-floating ideas in the theory portion of this project. It must have taken twice as long to read a single chapter as another book might have, because I kept looking away to write a note to myself later. Here are two passages I found particularly compelling. The first regards nature; the second regards how we acquire knowledge of the world around us.

<blockquote class="wp-block-quote">
  <p>
    &#8220;We have, then, to be wary of such a simple expression as &#8216;the natural environment&#8217;, for in thus conflating the two terms we already imagine ourselves to be somehow <em>beyond</em> the world, and therefore in a position to intervene in its processes (Ingold 1992a).&#8221;
  </p>
  
  <cite>Ingold (2000)<em>. The Perception of the Environment</em>. Chapter 1, page 20.</cite>
</blockquote>

<blockquote class="wp-block-quote">
  <p>
    &#8220;This is not to deny that information may be communicated &#8230; But information, in itself, is not knowledge &#8230; Our knowledgeability consists, rather, in the capacity to situate such information, and understand its meaning, within the context of a direct perceptual engagement with our environments. And we develop this capacity, I contend, by having things <em>shown</em> to us.&#8221;
  </p>
  
  <cite>ibid., page 21. </cite>
</blockquote>

This helped me a ton. Rather than the quite amorphous, nebulous idea of an app that &#8216;helps people connect with nature&#8217;, I can rather give a concrete purpose to my app in line with these principles. I am using AR as a tool to show things to the user, as an intermediary to facilitate &#8216;direct perceptual engagement&#8217; with the environment (which, in this case, is the garden).

Ingold relates this to his childhood experience of walking through the countryside with his father. His father would direct his attention to plants and fungi, telling Ingold to smell or taste them. He draws this as well to Australian Aboriginal Dreaming in which mentorship is done in much the same way. This is exactly the type of relationship I want to encourage between my app and the user.

#### 31/5/19

I took a step back from theory on Friday and opened Unity again. My goal for the day was to download the audio file I&#8217;d uploaded to Firebase, and by the end of the day I managed to get it working.

There are a few tricky things about downloading files from Firebase storage. The advantage is that you can easily store audio files. However, you have several choices for downloading them: a Unity stream, a byte array, a URL, or a local file.

Initially I thought I would have to use a byte array as I&#8217;d done with uploading the file. However, I quickly discovered how complicated it would be to manually convert the bytes to an AudioClip in Unity. Having experienced the complications of the Android local file system last week, and having no real understanding of MediaStreams in Unity, I was left with the download URL option.

When you use this option, Firebase storage creates a unique link from which a file can be downloaded. This requires the function `GetDownloadUrlAsync()`, which is asynchronous and therefore complicates the whole matter.

I&#8217;ve never been extremely well-versed in Unity Coroutines, but there weren&#8217;t many options at this point. It took a lot of fiddling. A word of advice: triple-check that you are using the correct file reference when you&#8217;re trying to download your file.

In the end I had two coroutines. The first coroutine contains the function listed above which would pass the outputted URL to the second coroutine to actually download the file. The biggest obstacle I faced here was that the first function was not returning the URL before I started the second coroutine. To solve this, I had to insert a while loop inside the first couroutine to ensure that the URL had been obtained before I tried to pass it on to the second coroutine:

<pre class="wp-block-code"><code>while (taskResult.CompareTo("") == 0) //taskResult is the URL.
{ 
    yield return null;
}
StartCoroutine(LoadAndPlayAudio(taskResult));</code></pre>

The second coroutine, `LoadAndPlayAudio()`, does not actually play the audio; it just sets a bool so show that the audio has been downloaded and is ready to play.

<pre class="wp-block-code"><code>IEnumerator LoadAndPlayAudio(string url) {
    using (UnityWebRequest www = UnityWebRequestMultimedia.GetAudioClip(url, AudioType.MPEG))
    {
        yield return www.SendWebRequest();

        if (www.isNetworkError)
        {
            Debug.Log(www.error);
        }
        else
        {
            AudioClip myClip = DownloadHandlerAudioClip.GetContent(www);
            audioSource.clip = myClip;
            readyToPlay = true;
        }
    yield return null;
}</code></pre>

Finally, for the purpose of testing, I just check in `Update()` if `readyToPlay` is true. Of course in the future I will change this to some type of event listener.

With some time to spare I was able to attempt to play the audio from the small ear speaker on the device. I won&#8217;t lie, I went ahead and found some code that manipulates the speakers used on Android. You can find it [here](https://forum.unity.com/threads/help-please-recording-mode-earpiece-mode-and-not-speaker-mode.462945/). All I had to do was use the `ToggleMode()` function provided in that link.

My codebase is starting to get really messy, though, with all of these tests. I will definitely have to spend a day or two cleaning up all of the unused things I&#8217;ve downloaded and played with and ensure that the code all follows the same conventions. Cleanliness is important; I expect in a few weeks time I won&#8217;t be able to read the code I&#8217;ve written today, if it stays how it is!

#### 3/6/19

For the final day of the week I met with my supervisor to discuss progress and look ahead at the project timeline. I also got some very useful feedback from my internal supervisor on my project proposal.

Given how much I&#8217;ve learned since I wrote the proposal, I&#8217;ll definitely have material to respond to the feedback and make a strong project plan.

In the meantime I composed a temporary set of deadlines for myself:

  * AR development: initial (ugly but functional MVP) prototype. 18/06/2019
      * Functionality for saving/loading AR objects is implemented
      * Audio files can be attached to digital objects
      * Everything has been tested in the garden. 
  * Literature review, first draft. Week of 18/06/2019. 
  * Once these things have been completed, I&#8217;d like to take some time making a lot of the design decisions, such as: 
      * What form the objects will take (3D models)
      * What (type of) content will be in the audio messages
      * Where the objects will be placed in the garden
      * User interface features 
  * In an ideal world, these decisions could be made and implemented by the following week (25/06/2019). However, we should at least expect that it would take another week (02/07/2019). 

This would leave about seven weeks remaining for testing, writing, and revising. 

Assuming I&#8217;d like to have a first draft of the dissertation written 3 weeks before the deadline (29/07/2019), this leaves 4 weeks for testing, analysis, and writing up from 02/07 to 29/07. 

What a tough schedule! But I&#8217;m looking forward to the challenge, and I think it&#8217;s achievable.

#### Review

Looking at this schedule and considering what I&#8217;ve achieved so far, I feel it&#8217;s a realistic appraisal. I&#8217;ve tried my best to ensure that the scope of the project is ambitious but within reason, and I think that&#8217;s been maintained for at least the last two weeks of the project.

Looking ahead, I&#8217;ll definitely have to spend some development time this week with some literature review writing in between. I&#8217;ll have to develop saving and loading the world in a way that ensures persistant locations of AR objects. If that goes smoothly, I&#8217;ll have time to look at recording audio files in Unity and using gestures to actually play the files (rather than a simple button as I have now).

Literature is fun too! I do feel that I need to step down from the philosophical world and get into some UX literature on creating questionnaire and interview questions, semiotics, and blended spaces. There&#8217;s so much to learn.

If you made it this far, thanks very much for reading and I&#8217;ll see you next week!