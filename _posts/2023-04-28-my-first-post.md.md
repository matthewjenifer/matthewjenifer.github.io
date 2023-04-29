---
layout: post           # The layout to use for the post (e.g., post, page)
title: Notes 2 Self         # The title of the post
subtitle: A Subtitle   # A subtitle for the post
date: 2023-04-28       # The date the post was published
last_modified_at: 2023-04-28 # The date the post was last modified
author: M. Jenifer       # The author of the post
categories:            # The categories the post belongs to
  - Programming
  - Web Development
tags:                  # The tags for the post
  - Jekyll
  - Tutorial
  - Example
image: ./images/OIP.png # The main image for the post
excerpt: This is an excerpt of the post that will be displayed on the homepage # The excerpt for the post
---

<p>Hello Earth.</p>

<p>I had a wordpress blog once and that was the opening post. I saw hello world and immediately heard Kate Bush's *"And Dream of Sleep"* in my head.. so I suppose thats as good as any place to start..</p>

<h2>Since 1999.</h2>

<p>(lets add a video clip here)</p>

<p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Magnam, fugiat nihil vel tempore possimus fuga natus autem aspernatur assumenda neque officiis reprehenderit error eligendi earum, inventore, velit rerum et magni.</p>

<p>How did you even get here ~~Sah~~ ..:</p>

<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<p>Where are you going ~~Sah~~ ..:</p>

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media




<p>Here are some tags for this post:</p>
<ul>
{% for tag in page.tags %}
  <li><a href="/tags/{{ tag }}/">{{ tag }}</a></li>
{% endfor %}
</ul>

<p><a href="/">Back to Home</a></p>
