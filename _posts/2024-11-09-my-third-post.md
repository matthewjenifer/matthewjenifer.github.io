---
layout: post
title: Man V Maschine - Ch 1
subtitle: This time, it's functional. 
image: ../images/success.jpg
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


<p>In the past few weeks, I have been working on creating a music theory tool for Native Instruments Maschine users, especially those (like me) who get lost navigating the complex world of music theory. Hopefully, this tool will help people understand how chords work harmonically and provide an easy, fun way to craft satisfying chord progressions, even if music theory feels intimidating or confusing. This is all en route to something much more functional and adaptive, but for starters, I made a vanilla JS tool called <a href="https://github.com/matthewjenifer/fif-finder-t2" target="_blank"><b>"Fif'Chord Finder"</b></a>.</p>

<div style="text-align: center;">
<img src="https://i.ibb.co/zsYF748/Progression-Frame-MAJ-MIN-w-Progkey.png">
</div>
<br>
<h2>Why Make This Tool?</h2>

<p>I set out to create this simple web app because of my experiences speaking with many Maschine users who struggle with utilizing the infamous Circle of Fifths. Maschine is a tremendously powerful music production tool, and it offers a lot of assistance in the form of preset scales and modal chord suggestions, but without a basic understanding of music theory, getting the best use of the device can feel overwhelming. This tool aims to solve that problem by giving users an easy and conditional way to explore the harmonic relationship between chords and make creative choices on their Maschine hardware without needing to understand the theory required to read the circle.</p>

<div style="text-align: center;">
<img src="https://cdn11.bigcommerce.com/s-luvfwivmyi/product_images/uploaded_images/240207-circle-fifths-02.jpg" height=300 >
</div>
<br>
<h2>Key Features So Far</h2>

<p> With the help of a coding assistant, I have made a lot of progress over the past few weeks, building this site from a basic idea. Here’s a summary of what we’ve done: </p> 

<h3>1. Transposable Chord Sets for Major and Minor Keys</h3>

<p>Maschine's chord matrix consists of 192 hard-coded chord structures that transpose according to the root note or song key: sets MAJ1 to MAJ8 for major keys and MIN1 to MIN8 for minor keys. Each individual set has 12 chords that provide multiple options when building a progression, all based in the key of C. This makes it easier for users of the device to change keys later on if they want, and this is precisely where I began.</p>

```javascript
// Established chord sets
const chordSets = {
    MAJ1: ['C', 'Emi', 'F', 'G', 'Ami', 'Esus4', 'Gadd9', 'Dmi', 'Fadd9', 'F6', 'Gsus4', 'G'],
    MAJ2: ['C', 'C/B', 'C/A', 'C/G', 'Fadd9', 'Fmi', 'Csus4', 'Ami7', 'Emi', 'F', 'Gsus4', 'G6'],
    MAJ3: ['C', 'Ami', 'Fma7', 'Gsus4', 'Ami add9', 'F6', 'Csus2', 'G', 'Dsus2', 'Bb add9', 'Gsus4', 'Fadd9'],
    MAJ4: ['C', 'G', 'Ami', 'F6', 'F', 'Ami/E', 'Dmi7', 'Ami/C', 'Gadd9', 'Ami7', 'G/B', 'Dmi/G'],
    MAJ5: ['C', 'D', 'F', 'C', 'Ab', 'Eb', 'Bb', 'F', 'G7sus4', 'Bb add9', 'F6', 'Cadd9'],
    MAJ6: ['C', 'G', 'Dmi', 'Ami', 'F', 'G/F', 'C/E', 'Ami7', 'Dmi7', 'Emi7', 'C/F', 'Gsus4'],
    MAJ7: ['C', 'G', 'Ami', 'Emi', 'F', 'C/E', 'Dmi', 'Dmi/C', 'G7/B', 'G', 'F/A', 'G7/B'],
    MAJ8: ['Cma9', 'C#dim', 'Dmi9', 'D#dim7', 'Emi9', 'C9#5', 'Fma7(add13)', 'Bb9', 'Emi7', 'A9', 'Dmi11', 'G7(b9,b13)'],
    MIN1: ['Cmi', 'Cmi/Eb', 'Fmi', 'G', 'Abma7', 'Eb', 'Gmi', 'Bb', 'F', 'Fmi/Ab', 'Cmi/G', 'G'],
    MIN2: ['Cmi', 'G+/B', 'Cmi/Bb', 'Cmi/A', 'Abma7', 'Ebma7', 'Fmi', 'Bb7', 'Cmi', 'Bbadd9', 'Abadd9', 'G7sus4'],
    MIN3: ['Cmi', 'Ab', 'Eb', 'Bb', 'F', 'Fmi', 'Cmi/G', 'Gsus4', 'Cmi', 'Cmi#5', 'Cmi6', 'Cmi7'],
    MIN4: ['Cmi', 'Eb', 'Bb', 'F', 'Ab', 'Abma7', 'Abmi7', 'Ebma7', 'Dsus4', 'D', 'Fmi/G', 'G+'],
    MIN5: ['Cmi', 'Bb', 'Ab6', 'Bb add9', 'Cmi', 'Dmi7', 'Cmi/Eb', 'Fmi', 'G', 'Ab ma7', 'B6/9', 'Csus4'],
    MIN6: ['Cmi', 'Fmi', 'Bb', 'Eb', 'Ab', 'Dmi7(b5)', 'Gadd(b9)', 'G', 'Ab/G', 'G7', 'Cmi/G', 'G7(b9)'],
    MIN7: ['Cmi9', 'Ab9', 'Cmi11', 'C7(#9,b13)', 'Fmi9', 'Ebma7/F', 'C11', 'Ami11', 'Ab7#11', 'G7#9', 'Cmiadd9', 'G7(b9,b13)'],
    MIN8: ['Cmi6/9', 'Dmi7(b5)', 'Cmi11/G', 'Cmi9', 'Fmi9', 'Abmi7', 'Ebmi7', 'Bbmi7(b5)', 'Ami11', 'Abma7#5', 'G7(b9,b13)', 'Cmi9ma7'],
};
```

<p>I initially started with a simple set of arrays, with the plan to later update them to function as objects, each containing the set number, pad number, chord name, Roman numeral, and smart key (not yet featured in the current output). This approach allowed me to get a working prototype quickly while also keeping future scalability in mind. As this project evolves, I'm certain these objects will become crucial for adding more detailed information and improving the flexibility of the tool. The transition from arrays to objects was a key step in ensuring that the tool could handle more complex data moving beyond this initial feature buildout.</p>

<p>Since I based this tool on a pre-existing device, I knew any app I developed would need to function similarly to the chord bank layout in Maschine. My tool needed to automatically adjust all 192 chords across the different sets according to a given root input, while maintaining the general structure of each bank. Admittedly, this had me stumped for the better part of a year, but sometimes it helps to put it aside and start from scratch. Once I had the logic to transpose across chord sets, the rest came (relatively) easily.</p>


<div style="text-align: center;">
<img src="https://i.ibb.co/smsN3Lv/modal-interchange.png">
</div>

<h6><em>(Above is a screencap from a thread on modal exchange I generated with NotebookLM. My sources were the previously stated fixed chord sets, the Circle of Fifths, and a book on borrowing chords for jazz compositions. This should offer you an example of the kind of progressions users might use my tool to construct and why.)</em></h6>
<br>
<h3>2. Chord Cloning and Simplification</h3>

<p>Next, I created functions to simplify the transposed chords for use in the Circle of Fifths function I knew I would implement later. When run, this code mirrors the simplified and complex versions of the new set of chords (transposed according to root input), then provides relative chord information alongside the chord set and pad number for users to access, like searching through the index of a textbook. Written out this way, it sounds pretty straightforward, but the order of these functions took some time to develop, if I'm honest.</p>

```javascript
// Loop through the circle to find a match
for (let i = 0; i < circle.length; i++) {
    if (circle[i].major === simplifiedRoot || circle[i].enharmonicMajor === simplifiedRoot) {
        currentKey = circle[i];
        chordType = 'major';
        // console.log('Found Major Match:', currentKey);
        break;
    } else if (circle[i].minor === simplifiedRoot || circle[i].enharmonicMinor === simplifiedRoot) {
        currentKey = circle[i];
        chordType = 'minor';
        // console.log('Found Minor Match:', currentKey);
        break;
    }
}
if (!currentKey) {
    console.log('Chord not found in the circle of fifths.');
    return null;
}
```


<p>When looking at the Circle of Fifths, it was clear to me that all suffixes for complex chordal information should be identified separately, this way all chords could be broken down into a base format (major or minor). By simplifying the transposed chords, my Circle of Fifths function would simply need to match against the base format and return a corresponding key. This process helped me focus on efficiency and accuracy. The goal was to make harmonic exploration feel seamless, whether users wanted a quick reference or a deeper dive into chord relationships.</p>

<h3>3. Identifying Relative and Neighboring Chord Matches</h3>

<p>The most important part of this tool's functionality was creating a logical Circle of Fifths function. For it to work properly, these neighboring and relative relationships had to make sense. This involved a lot of cross-referencing, double- and triple-checking (at one point, I had to compile and recompile chord lists with a fine-toothed comb against pictures of the device on my phone), and many, many errors and debugging console logs. In a way, I kind of built this tool by debugging to figure out my next step!</p>

<p>For example, I encountered several problems concerning slash `(V/V)` chords and complex suffixes involving sharps and flats like 'ma7b5#9'. At one point, there was a weird issue where the chord `'Bsus4'` would show up when it should have been `'D'`. </p>

```javascript
function simplifyChord(chord) {
    const rootMatch = chord.match(/^[A-G][b#]?/);
    if (!rootMatch) return chord;

    const root = rootMatch[0];
    const isMinor = chord.includes('mi') && !chord.includes('maj');

    specificSuffixes.forEach(suffix => {
        const regex = new RegExp(suffix + '(?!\\w)', 'gi');
        chord = chord.replace(regex, '');
    });
    

    chord = chord.replace(/\/[A-G][b#]?/g, '');
    const finalRoot = enharmonicMap[root] || root;

    return isMinor ? `${finalRoot}mi` : finalRoot.trim();
}
```

<p>Fixing simple (and sometimes not-so-simple) errors like these ultimately served to make the tool more accurate and taught me to truly take things step by step. Much like composing notation, building software requires a developer to get very specific (as opposed to aiming for the BIG "finished" picture). To be honest, this is not something I'm apt to do. Having a lot to recall about music theory and programming syntax, it felt like forever when, in reality, the process of debugging and updating ultimately took about 5-6 days! But once I had the script logic down (about 10 iterations in), I felt like I was walking on air. It was such a small breakthrough, but small breakthroughs feel great as a novice dev.</p>

<div style="text-align: center;">
<img src="https://preview.redd.it/music-theory-app-sneak-peak-v0-9syeztns0sxd1.png?width=464&format=png&auto=webp&s=42f68b638ecb31f04a61e1f9cd87e6d62b098cfc">
</div>
<br>
<h2>So...What’s Next?</h2>

<p>Even though I’ve definitely come a long way (hence choosing to commemorate with my first blog in like a year), there’s still so much more to do. Throughout this small project, I’ve learned a lot about how important it is to start with the tiniest possible function and add from there when developing something original. I'd heard this throughout my CompSci learning journey, but it really didn't settle in until now. It's been hard to articulate an idea that made little sense to anyone. I had to build something to show what I meant—and finally, I have. But we're definitely not done yet.</p>

<p> Moving forward, I want to create a React app version that's mobile-responsive and has more than just this <a href="https://fif-finder-t2.vercel.app" target="_blank"><b>'Chord Finder'</b></a>  feature. That being said, I still intend to update and keep improving this tool along the way (for example, I started designing pad thumbnails to appear on hover and have a few other ideas in mind).</p>

<div style="text-align: center;">
<img src="https://i.ibb.co/3r4b6WS/faceplates.png">
</div>

<p>The fully fleshed-out app will also have a visual display that looks like the Maschine hardware most users will have in front of them. This will make tandem use of the software and hardware much more seamless. I know better than most how crucial this is when chasing inspiration. Every second counts, and I aim to make extra time for everybody.</p>

<!-- <div style="text-align: center;">
<img src="https://i.ibb.co/9cqxB28/theoryappfull.png" height=300>
</div> -->

<p>What excites me the most is making tools to bridge the gap between what bedroom producers hear in their heads and what they create in their DAWs. I want users to feel confident, inspired, and excited to explore all that theory has to offer. But most importantly, I want them to feel empowered!</p>

<p>Here are some tags for this post:</p>
<ul>
{% for tag in page.tags %}
  <li><a href="/tags/{{ tag }}/">{{ tag }}</a></li>
{% endfor %}
</ul>

<p><a href="/">Back to Home</a></p>
