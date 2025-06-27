---
layout: post
title: I Built My Second Theory Tool in 24 Hours
subtitle: Why a Sleep-Deprived Producer Built a Web App No One Asked For
image: ../images/disk thumb.png
date: 2025-06-26
last_modified_at: 2025-06-26
author: M. Jenifer
categories:
  - Development
  - Music Production
tags:
  - Maschine
  - Web App
  - Music Tech
  - Open Source
  - Tone.js
  - Tailwind CSS
  - Git
  - AI
  - DeepSite
---

<link rel="stylesheet" type="text/css" href="./_css/styles.css">


<em>I wasn’t planning to build another web app these past two days, but I couldn't sleep. If you’ve ever tried loading custom chords into Native Instruments Maschine, you already know it sucks. The process is slow and just tedious enough to make you put off engaging with the new feature. But even if you haven’t, take my word for it. Better yet, watch this 60 sec video.</em>

<div style="position: relative; width: 100%; max-width: 100%; overflow: hidden; height: 0; padding-bottom: 56.25%;">
  <iframe src="https://www.youtube.com/embed/er8DLKgfzX0"
          style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen></iframe>
</div>

<br>
<p>There's a bit of a debate going on at the moment. Famed beatmaker Timbaland has caught the ire of many up and comers for his embrace and endorsement of generative music and "AI" use in the production realm. But when I pan out and look at my journey bootcamp up to the last few days—I realize the first hurdle I faced (faster this time around) was mapping my chord tools to Maschine before gaining clarity on the C3/C4 issue (more on that later). Enter DeepSite—an open source LLM playground that, to be honest, did most of the heavy lifting for this single page app I made, while I directed from the pilot's seat. Before I got into coding I would've thought this would make me less of a “real” coder, but therein lies the beauty of what I now understand: for more senior devs, using new tools is half the job. 70% of code is borrowed anyway.</p>

<p>So since I knew I wasn't going to get much rest Tuesday morning, I decided to tackle a familiar issue again. I'd already found success with <a href="https://github.com/mikhailsoldatkin/maschine_chords_converter" target="_blank">an executable going around online</a> (you create a bunch of folders, export MIDI files one by one on your device or MIDI plugin, drop the exe file in the folder hierarchy, run the exe file, command line opens and THEN you have your JSON files), but after all the steps involved it still required tweaking. Admittedly, it was less work than the advised note-by-note process, but the chords were sometimes out of order and the octaves were all over the place. And I personally know more than a few users who would rather switch to Akai than open up an IDE editor (or learn how to use one). So..</p>

<br>
<div style="text-align: center;">
<a href="https://customchordgenerator-v1.vercel.app/" target="_blank"><img src="https://i.ibb.co/TMvzJp6Z/disk-thumb.png"></a>
</div>
<em>Notice anything strange about this image? AI is responsible for 50% of it. I used photopea to edit it a bit. Give it a floppy disk overlay, but the original version had a piano keyboard with no G# originally. And I wasn't having that. </em>
<br>

<h4>I Did the Work Because You Shouldn't Have To</h4>

<p>Maschine isn’t interested in your “Dmin9” or “F#sus4” loop unless you feed it exactly what it understands. Like any machine it deals in numbers, but in the case of version 3.1's User Chord feature, it specifically needs a set of MIDI note objects contained in one of 12 JSON files.</p>

<p> A unique feature of Native Instruments products is that they program middle C as C3, not the standard C4 many DAWs use. So if your mapping assumes C4, everything ends up an octave off. This may seem minuscule at first, but that difference of 8 is crucial when trying to write scripts that can predict what future users actually want to hear:</p>

<p> Ultimately we're talking about the difference between this: </p> 

```javascript
{
  "chords": [
    {
      "name": "Amaj7",
      "notes": [
        -15,
        1,
        4,
        8
      ]
    }
  ],
  "name": "My Set",
  "typeId": "native-instruments-chord-set",
  "uuid": "3194f0fd-4911-4299-aa34-0892ffdbddf8",
  "version": "1.0.0"
}

```

<p> ..and this: </p> 

```javascript
 {
  "chords": [
    {
      "name": "Amaj7",
      "notes": [
        -3,
        13,
        16,
        20
      ]
    }
  ],
  "name": "My Set",
  "typeId": "native-instruments-chord-set",
  "uuid": "3194f0fd-4911-4299-aa34-0892ffdbddf8",
  "version": "1.0.0"
}

```

<h2>MIDI Note Hell.</h2>
<br>
<ol>
<li><h4>What Used to Trip Me Up</h4><br>
I thought mapping chords to MIDI numbers would be copy-paste simple when I first started down this path. Maschine uses its own unique mapping, the “documentation” is often just forum scraps, and few devs I know are as curious as I am about music theory-related problems. Ultimately I ended up studying my own test JSON files, analyzing what was numerically generated by the provided preset chord voicings, and cross-referencing my way to a conclusion. If you’ve ever done code archaeology with headphones on—or even made the type of lofi beats many coders listen to—you know the feeling. I built my own note map, broke it a few times, rebuilt it, tested again, broke it again. And then suddenly, it worked.</li>
<br>
<li><h4>Enlisting AI to let Users Be Human.</h4><br>
People often write “C#min7” or “Dbm7” or “c   maj7” with typos, weird spacing, whatever. My work on my last web app taught me: if you don’t approach this right, most apps just spit out errors or ignore you. I wanted this one to work seamlessly. The target user barely has time to select each chord pad by pad, so who wants to fiddle with a web app that doesn't understand your chord shorthand? I leveraged my newfound prompting skills to both build preemptive guardrails into the code and sanity-check the process with ChatGPT before my brain could have time to get fried on a single logic error.</li>
<br>
<div style="text-align: center;">
<img src="https://i.ibb.co/xSPqLLr5/reddit.png">
</div>
<br>
<br>
<li><h4>Letting It Look "Ugly."</h4><br>
I enjoy UI a bit, but I didn’t really have time to nitpick CSS shading and general layout at the start. Tailwind CSS to the rescue. I copied what worked from open source sites, adjusted as needed, and checked it on my phone around 2am. The result not only looked fine—it worked pretty well. I figured I'd finally get some rest and clock back in the following day to tweak as I went along.</li>
<br>
<h2>Day 2</h2> 
<br>
<li><h4> Hosting and Hiccups.</h4><br>
Deployment is usually the “fun” part—if your idea of fun is being trolled by cache errors. Thankfully, Vercel handled most of it, but I still had to search forums to fix asset paths. Once I got my bearings, the process was as painless as I remembered, and <a href="https://github.com/matthewjenifer/customchordgenerator_v1" target="_blank">I was live and running in no time.</a> Well, kinda.</li>
<br>
<li><h4>Git Drama.</h4><br>
I made all the classic mistakes. Tried to push, got rejected. Pulled, made it worse. In the end, I just deleted everything and cloned fresh. If you ever feel stupid doing this, don’t—every developer does it and just doesn’t talk about it. Once again, anything I forgot, I knew between ChatGPT and Perplexity I could arrive at an answer quickly. The rest was muscle memory, and it made me reflect on how long things took my first week in bootcamp.</li>
</ol>

<h3>The Stack (If You Care)</h3>

<ul>
<li>Vercel for hosting, because it’s one click and done.</li>
<li>Tailwind CSS for not having to think about pixels.</li>
<li>Tone.js so users could hear chords before exporting them.</li>
<li>DeepSite for AI-assisted sanity checks and batch boilerplate work.</li>
<li>VSCode</li>
<li>StackOverflow, Native Instruments community forum, and of course ChatGPT.</li>
</ul>

<br>
<div style="text-align: center;">
<img src="https://i.ibb.co/9kRHkvHS/Screenshot-20250627-050208-Chat-GPT.jpg">
</div>
<br>
<br>

<h2>Isn't This Overkill for a Trivial Feature Update?</h2>

<p>I could see why someone might say that. But for me, it was only half about that. Whether it’s chopping a sample or picking apart the software we chop samples on, it’s all problem-solving to me. I imagine it’s easy to look at a simple app like this and think, “what's the big deal?” But if you’re someone who needed this solution, and it now exists, it's more than big enough. Before it was even fully deployed, someone on Reddit actually offered to pay for this solution, but I'd already planned for it to be free. (Actually, I'm hoping to use it as a lead generator, but even if I don’t get a bite on that hook, there's a tip jar link if anyone wants to buy me coffee.) This is just how problems get solved: not by waiting for the solution to show up, but by giving yourself permission to show up—and to tinker until something works. Which I'm happy to say I did.</p>

<br>
<div style="text-align: center;">
<img src="https://i.ibb.co/N2mDWCz6/redditreplies.png">
</div>
<br>

<h3>So... Next?</h3>

<p>Well, I don’t have any grand plans for this browser app beyond what it already does, honestly. If enough people use it, I’ll add features: more chord type functionality, maybe a way to see chords on a piano, or change voicing. That might make for a fun personal puzzle. This is my first successful implementation of Tone.js actually, so I'm pretty happy with that for now. It all makes so much more sense to me than I remember it making at first. I may drop the link a few places online and see who engages. Take it from there.</p>

<h2>Final Thoughts</h2>

<p>If anything in your workflow feels like self-torture, maybe there's a way to build your own way out. I'm not ashamed to say I'm proud of myself every time I do that. And it's always easier than waiting for someone else. More fun too, if you ask me.</p>

<p>As for the debate on Suno, Timbaland, and yadda yadda yadda... If you ask me, using LLMs and Generative AI is just part of the toolkit now. It always depends on who's using it, and I say don’t let anybody make you feel weird about it.</p>

<p>Here are some tags for this post:</p>
<ul>
{% for tag in page.tags %}
  <li><a href="/tags/{{ tag }}/">{{ tag }}</a></li>
{% endfor %}
</ul>

<p><a href="/">Back to Home</a></p>
