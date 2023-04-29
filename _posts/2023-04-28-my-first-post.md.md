---
layout: post
title: EXPERIMENT V
subtitle: A Subtitle
date: 2023-04-28
last_modified_at: 2023-04-29
author: M. Jenifer
categories:
  - Programming
  - Web Development
tags:
  - Jekyll
  - Kate Bush
  - Latin
image: ../images/OIP.png
---

<link rel="stylesheet" type="text/css" href="./_css/styles.css">

<p>Hello Earth.</p>

<p>I had a wordpress blog once and that was the opening post. I saw hello world and immediately heard Kate Bush's *"Hello Earth"* in my head.. so I suppose thats as good as any place to start..</p>

<h2>The following song is not Hello Earth.</h2>

<div class="video-container">
  <iframe width="100%" height="auto" src="https://www.youtube.com/embed/oKOmhHWFuB4?autoplay=1" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

</div>

<br>

<p>Pergam et ero honestus, 64-82% huius diarii componetur ope chatbotarum et ai. non solum quia piger sum sed etiam quod videre cupio quis hoc legerit. quoniam in alia lingua. sed etiam inopinata expecta. multum futurae meae nuntia encryption includet quia cur non?</p>

<!-- <p>How did you even get here ~~Sah~~ ..:</p>

<ul>
  <li>Making Dubs</li>
  <li>MIDI/Programming</li>
  <li>A/V</li>
</ul> -->

<p>Here are some tags for this post:</p>
<ul>
{% for tag in page.tags %}
  <li><a href="/tags/{{ tag }}/">{{ tag }}</a></li>
{% endfor %}
</ul>

<p><a href="/">Back to Home</a></p>
