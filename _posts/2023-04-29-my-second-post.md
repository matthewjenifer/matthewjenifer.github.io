---
layout: post
title: Overcomplicationalism
subtitle: A Gentleman's Ode 
image: ../images/oversimp-thumbnail.jpg
date: 2023-04-29
last_modified_at: 2023-04-29
author: M. Jenifer
categories:
  - Blogging
  - Web Development
tags:
  - ChatGPT
  - Content Creation
  - SEO
  - UI Design
  - Github
  - Social Media Marketing
---

<link rel="stylesheet" type="text/css" href="./_css/styles.css">

<img src="https://raw.githubusercontent.com/matthewjenifer/matthewjenifer.github.io/main/images/oversimp.png">

<h1>Yeah so..</h1>

<p>I've been working on this blog for a total of 72 hours and I started thinking..building a blog from scratch can feel unnecessarily complicated.Right after realizing this, I understood why: purpose. There is so much more to building a blog from scratch than meets the eye. Here are some things to consider::</p>

<p>Firstly, when you build a blog from scratch, you have to consider the technical aspects of it. Choosing a domain name, web hosting, and designing the layout are essential first steps. I opted for GitHub because it's free. However, for those unfamiliar with web development, this can feel overwhelming.</p>

<h2>Here's a list of every blogging platform I've used before doing it this way (the ones I can remember at least..)</h2>

<ul>
  <li>Homestead</li>
  <li>BlackPlanet (that kinda counts right?)</li>
  <li>Wordpress</li>
  <li>Blogger</li>
  <li>Tumblr (good ol tumblr)</li>
  <li>Wix (My site had a blog, an under used blog but still a blog)</li>
</ul> 

<ul>
<li>I feel like Facebook and Twitter count technically (micro-blogging), but tbh I havent done too much of that in years unless you count my random non business related posts on Linkedin</li>
</ul>

<img src="https://starecat.com/content/wp-content/uploads/normal-people-adding-7-plus-6-equals-13-me-different-logic-family-guy.jpg">

<p>Which brings me to my second point: Writing a blog is time-consuming. It takes effort to come up with ideas, research, write, and edit content. Luckily, AI is here to help. But without SEO—crucial for driving traffic—your post might never be seen. I still need to add RSS, which brings me to the checklist:
</p>

<h3>..might as well bring that check list back out:</h3>


- [ ] we need RSS
- [ ] we need a navbar 
- [ ] social tray?
- [ ] tag cloud??
- [ ] ...

<p>Anyway, promoting the blog and growing a readership is probably the?(MY) biggest hurdle. Techniques like social media marketing, guest blogging, and networking help with exposure, but it requires consistent effort, even with the assistance of a chatbot.</p>

<img src="https://raw.githubusercontent.com/matthewjenifer/matthewjenifer.github.io/main/images/bloggingthehardway.png">
<p>Ultimately, building a successful blog takes technical knowledge, content creation skills, SEO, and good design. It may seem daunting, but there are plenty of resources online to help. And that's part of the fun.
</p>




<p>Here are some tags for this post:</p>
<ul>
{% for tag in page.tags %}
  <li><a href="/tags/{{ tag }}/">{{ tag }}</a></li>
{% endfor %}
</ul>

<p><a href="/">Back to Home</a></p>
