---
layout: post
title: Man V Maschine
subtitle: Chapter 1 
# image: ../images/placeholder.jpg
date: 2024-11-09
last_modified_at: 2024-11-09
author: M. Jenifer
categories:
  - Music Theory
  - Web Development
tags:
  - ChatGPT
  - Photopea
  - Canva
  - Circle of Fifths
  - UI Design
  - Github
  - Native Instruments
  - Maschine MK3
---

<link rel="stylesheet" type="text/css" href="./_css/styles.css">

<img src="https://raw.githubusercontent.com/matthewjenifer/fif-finder-t2/refs/heads/main/images/MK3_frame.png" height=300 style="display: block; margin: auto;">

<p>In the past few weeks, I have been working on creating a music theory tool for Native Instruments Maschine users, especially those (like me) who get lost navigating the complex world of music theory. Hopefully, this tool will help people understand how chords work harmonically together and provide an easy, fun way to craft chord progressions, even if music theory feels intimidating or confusing. This is all en route to something much more functional and adaptive, but for starters, I made a vanilla JS tool called <b>"Fif'Chord Finder"</b>.</p>


<h2>Why Make This Tool?</h2>

<p>I set out to create this simple app because of my own experiences speaking with many Maschine users who struggle with how exactly to use the infamous circle. Maschine is a tremendously powerful music production tool, and it offers a lot of assistance in the form of preset scales and modal chord banks, but without a basic understanding of music theory, figuring out which chords go well together can feel overwhelming. This tool aims to solve that problem by giving users an easy and interactive way to explore the harmonic relationship between chords and make creative choices on their Maschine hardware without needing to understand the theory required to read the Circle of Fifths.</p>
<div style="text-align: center;">
<img src="https://cdn11.bigcommerce.com/s-luvfwivmyi/product_images/uploaded_images/240207-circle-fifths-02.jpg" height=300 >
</div>
<h2>Key Features So Far</h2>

<p> With the help of ChatGPT, I have made a lot of progress over the past few weeks, building this site from a basic idea. Here’s a summary of what we’ve done: </p> 
<div style="text-align: center;">

<img src="https://i.ibb.co/zsYF748/Progression-Frame-MAJ-MIN-w-Progkey.png" height=300>
</div>

<h3>1. Chord Sets for Major and Minor Keys</h3>


<p>Maschine's chord matrix consists of 192 hard-coded chord structures that transpose according to the root note: MAJ1 to MAJ8 for major keys and MIN1 to MIN8 for minor keys. Each individual set has 12 chords that provide several options when building a progression, all starting in the key of C. This makes it easier for users of the device to change keys later on if they want, and this is precisely where I began.</p>

<!-- <img src="https://cdn11.bigcommerce.com/s-luvfwivmyi/product_images/uploaded_images/240207-circle-fifths-02.jpg" height=300> -->

<h3>2. Changing Keys Easily</h3>

<p>One of the most important features is allowing users to easily change the key of the chord sets. Again, I based this tool on a pre-existing device, so I knew any app I developed would need to function similarly to the chord bank layout in Maschine. Instead of being stuck in one key, users can choose any starting note they like, so my tool needed to automatically adjust all 192 chords across the different sets. Admittedly, this had me stumped for the better part of a year, but sometimes it helps to put it aside and start from scratch. Once I had the logic to transpose across chord sets, the rest came (relatively) easily.</p>

<div style="text-align: center;">
<img src="https://i.ibb.co/xJd1GYf/chordcode.png" >
</div>

<h3>3. Understanding How Chords Work Together</h3>

<p>Another big part of building this tool was creating a Circle of Fifths function and making sure those relationships made sense. This involved a lot of cross-referencing, double- and triple-checking, and many errors in the console.</p>

<p>For example, we fixed several problems concerning slash chords, `(V/V)` chords, and complex suffixes involving sharps and flats. At one point, there was an issue where the chord `'Bsus4'` would come up when it should have been `'D'`. Fixing simple errors like these made the tool more accurate and also taught me to truly take things step by step. Much like making music, building software requires a developer to get very specific (as opposed to aiming for the BIG "finished" picture—something I'm apt to do).</p>

<p>Having a lot to recall about music theory and programming, it felt like forever when, in reality, the process of debugging and updating really only took 6-7 days! But once I had the script file down (13 versions in), I felt like I was walking on air. It was such a small breakthrough, but small breakthroughs count.</p>
<div style="text-align: center;">

<img src="https://preview.redd.it/music-theory-app-sneak-peak-v0-9syeztns0sxd1.png?width=464&format=png&auto=webp&s=42f68b638ecb31f04a61e1f9cd87e6d62b098cfc" height=300>
</div>

<h2>So...What’s Next?</h2>

<p>Even though I’ve definitely come a long way (hence choosing to commemorate with my first blog in a year), there’s still more to do. Throughout this project, I’ve learned a lot about how important it is to start with the smallest possible function and add from there when developing something for users. I'd heard this all throughout my learning journey, but it really didn't settle in until now. It was hard to explain an idea that made little sense to anyone. I had to build something to show what I meant—and finally, I have. But we're definitely not done yet. Moving forward, I want to create a full-stack React app that's mobile-responsive and has more than just this Fif'Chord Finder feature, but the plan is to keep improving this tool along the way. (For example, I started designing pad thumbnails to appear on hover and have a few other ideas in mind.)</p>

<p>My plan for the final app is to add a visual display that looks like the Maschine hardware so users can see and interact with the chords in a more natural way. This will make using the software and hardware together much more seamless. This is crucial when chasing inspiration—every second counts, and I want to free up some. For everybody.</p>

<p>In the end, this tool is all about making it easier to bridge the gap between what you hear in your head and what you create on your Maschine. I want users to feel confident, inspired, and excited to explore all that theory has to offer. Most importantly, I want them to feel empowered to create their best music yet!</p>

<p>Here are some tags for this post:</p>
<ul>
{% for tag in page.tags %}
  <li><a href="/tags/{{ tag }}/">{{ tag }}</a></li>
{% endfor %}
</ul>

<p><a href="/">Back to Home</a></p>
