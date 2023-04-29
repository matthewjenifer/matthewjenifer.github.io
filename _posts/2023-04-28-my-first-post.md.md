---
layout: post
title: EXPERIMENT IV
subtitle: A Subtitle
date: 2023-04-28
last_modified_at: 2023-04-28
author: M. Jenifer
categories:
  - Programming
  - Web Development
tags:
  - Jekyll
  - Tutorial
  - Example
image: ./images/OIP.png
excerpt: This is an excerpt of the post that will be displayed on the homepage
---

<p>Hello Earth.</p>

<p>I had a wordpress blog once and that was the opening post. I saw hello world and immediately heard Kate Bush's *"Hello Earth"* in my head.. so I suppose thats as good as any place to start..</p>

<h2>The following song is not Hello Earth.</h2>

<iframe width="560" height="315" src="https://www.youtube.com/embed/oKOmhHWFuB4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>


<p>Pergam et ero honestus, 64-82% huius diarii componetur et componetur ope chatbotarum et ai. non solum quia piger sum sed etiam quod videre cupio quis hoc legerit. quoniam in alia lingua. sed etiam inopinata expecta. multum futurae meae nuntia encryption includet quia cur non?</p>

<p>How did you even get here ~~Sah~~ ..:</p>

<ul>
  <li>Making Dubs</li>
  <li>MIDI/Programming</li>
  <li>A/V</li>
</ul>

<p>Are you even ~~Sah~~ ? ..:</p>

- [x] Random AF
- [ ] Cryptic
- [ ] Unique

<p>Here are some tags for this post:</p>
<ul>
{% for tag in page.tags %}
  <li><a href="/tags/{{ tag }}/">{{ tag }}</a></li>
{% endfor %}
</ul>

<p><a href="/">Back to Home</a></p>
