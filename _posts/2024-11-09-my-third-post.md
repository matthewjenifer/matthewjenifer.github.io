---
layout: post
title: Man V Maschine - Ch 1
subtitle: This time, it's functional. 
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

<img src="https://raw.githubusercontent.com/matthewjenifer/fif-finder-t2/refs/heads/main/images/MK3_frame.png" style="display: block; margin: auto;">

<p>In the past few weeks, I have been working on creating a music theory tool for Native Instruments Maschine users, especially those (like me) who get lost navigating the complex world of music theory. Hopefully, this tool will help people understand how chords work harmonically together and provide an easy, fun way to craft chord progressions, even if music theory feels intimidating or confusing. This is all en route to something much more functional and adaptive, but for starters, I made a vanilla JS tool called <a href="https://github.com/matthewjenifer/fif-finder-t2" target="_blank"><b>"Fif'Chord Finder"</b></a>.</p>

<div style="text-align: center;">

<img src="https://i.ibb.co/zsYF748/Progression-Frame-MAJ-MIN-w-Progkey.png">
</div>

<h2>Why Make This Tool?</h2>

<p>I set out to create this simple web app because of my own experiences speaking with many Maschine users who struggle with how exactly to use the infamous Circle of Fifths. Maschine is a tremendously powerful music production tool, and it offers a lot of assistance in the form of preset scales and modal chord banks, but without a basic understanding of music theory, figuring out which chords go well together can feel overwhelming. This tool aims to solve that problem by giving users an easy and conditional way to explore the harmonic relationship between chords and make creative choices on their Maschine hardware without needing to understand the theory required to read the circle.</p>
<div style="text-align: center;">
<img src="https://cdn11.bigcommerce.com/s-luvfwivmyi/product_images/uploaded_images/240207-circle-fifths-02.jpg" height=300 >
</div>
<h2>Key Features So Far</h2>

<p> With the help of a coding asistant, I have made a lot of progress over the past few weeks, building this site from a basic idea. Here’s a summary of what we’ve done: </p> 

<h3>1. Transposable Chord Sets for Major and Minor Keys</h3>

<p>Maschine's chord matrix consists of 192 hard-coded chord structures that transpose according to the root note or song key: sets MAJ1 to MAJ8 for major keys and MIN1 to MIN8 for minor keys. Each individual set has 12 chords that provide multiple options when building a progression, all based in the key of C. This makes it easier for users of the device to change keys later on if they want, and this is precisely where I began.</p>
<div style="text-align: center;">
<img src="https://i.ibb.co/pX8SkJW/chordsets2.png">
</div>


<p>One of the most important features is allowing users to easily change the key of the chord sets. Since I based this tool on a pre-existing device, I knew any app I developed would need to function similarly to the chord bank layout in Maschine. Instead of being stuck in one key, users can choose any starting note they like, so my tool needed to automatically adjust all 192 chords across the different sets. Admittedly, this had me stumped for the better part of a year, but sometimes it helps to put it aside and start from scratch. Once I had the logic to transpose across chord sets, the rest came (relatively) easily </p>


<div style="text-align: center;">
<img src="https://i.ibb.co/smsN3Lv/modal-interchange.png">
</div>
<p><i>(above is a screencap from a thread on modal exchange I generated with NotebookLM, using the fixed chord sets, the circle of fifths and a book on Jazz. This should offer an example of of the kind of progressions users might use my tool to construct and why.).</i></p>
<h3>2. Chord Cloning and Simplification</h3>
<p>I created functions to simplify the transposed chords for use in the Cicrle of Fifths function I would build later. The code would mirror the simplified and complex versions of the new set of chords transposed according to root input, then provide relative chord information along side set and pad number for users to access easy like searching through the index of textbook. Written out like that it sounds pretty straightforward but the order of these functions took some time to develop.</p>

<div style="text-align: center;">
<img src="https://i.ibb.co/Xx8f4fY/chordsets3.png" >
</div>

<h3>3. Identifying Relative and Neighboring Chord Matches</h3>

<p>The most important part of this tool's functionality was creating a logical Circle of Fifths function. In order to work properly these neighboring and relative relationships had to make sense. This involved a lot of cross-referencing, double- and triple-checking (at one point I had to compile and re compile chord lists to match with a fine toothed comb against pictures of the device on my phone), and many many errors and debugging console logs. In a way, I kind of built this tool by debugging to figure out my next step!</p>

<p>For example, I encountered several problems concerning slash `(V/V)` chords, and complex suffixes involving sharps and flats like 'majb5#9'. At one point, there was a weird issue where the chord `'Bsus4'` would show up only when it should have been `'D'`. Fixing simple (and sometimes not so simple) errors like these ultimately served to madke the tool more accurate and taught me to truly take things step by step. Much like composing notation, building software requires a developer to get very specific (as opposed to aiming for the BIG "finished" picture). To be honest, this is not something I'm apt to do.</p>

<p>Having a lot to recall about music theory and code syntax, it felt like forever when, in reality, the process of debugging and updating ultimately took about 5-6 days! But once I had the script logic down (about 10 iterations in), I felt like I was walking on air. It was such a small breakthrough, but small breakthroughs feel great as a novice dev.</p>
<div style="text-align: center;">

<img src="https://preview.redd.it/music-theory-app-sneak-peak-v0-9syeztns0sxd1.png?width=464&format=png&auto=webp&s=42f68b638ecb31f04a61e1f9cd87e6d62b098cfc">
</div>

<h2>So...What’s Next?</h2>

<p>Even though I’ve definitely come a long way (hence choosing to commemorate with my first blog in like a year), there’s still so much more to do. Throughout this small project, I’ve learned a lot about how important it is to start with the tiniest possible function and add from there when developing something for original. I'd heard this all throughout my compsci learning journey, but it really didn't settle in until now. It's been hard to articulate an idea that made little sense to anyone. I had to build something to show what I meant—and finally, I have. But we're definitely not done yet. Not by a long shot. Moving forward, I want to create a full-stack React app that's mobile-responsive and has more than just this <a href="https://fif-finder-t2.vercel.app" target="_blank"><b>'Chord Finder'</b></a> feature. That being said I still intend to update and keep improving this tool along the way. (For example, I started designing pad thumbnails to appear on hover and have a few other ideas in mind.)</p>

<div style="text-align: center;">
<img src="https://i.ibb.co/3r4b6WS/faceplates.png">
</div>

<p>The fully fleshed out final app will also have a visual display that looks like the Maschine hardware most users will have in front of them. This will make tandem use of the software and hardware much more seamless. I know better than most how crucial this is when chasing inspiration. Every second counts, and I aim to make extra time for everybody.</p>

<!-- <div style="text-align: center;">
<img src="https://i.ibb.co/9cqxB28/theoryappfull.png" height=300>
</div> -->

<p>What excites me the most is making tools to bridge the gap between what bedroom producers hear in their heads and what they create in their DAWS. I want users to feel confident, inspired, and excited to explore all that theory has to offer. But most importantly, I want them to feel empowered!</p>

<p>Here are some tags for this post:</p>
<ul>
{% for tag in page.tags %}
  <li><a href="/tags/{{ tag }}/">{{ tag }}</a></li>
{% endfor %}
</ul>

<p><a href="/">Back to Home</a></p>
