---
layout: post
title: Notes 2 Self
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

<h2>Since 1999.</h2>

<p>{% raw %}{% include youtube.html id="rpcUTWHlbvI" %}{% endraw %}</p>

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
