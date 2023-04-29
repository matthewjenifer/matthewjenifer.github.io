---
layout: post           # The layout to use for the post (e.g., post, page)
title: My Post         # The title of the post
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
image: /images/OIP.png # The main image for the post
excerpt: This is an excerpt of the post that will be displayed on the homepage # The excerpt for the post
---

<p>Welcome to my first post!</p>

<p>This is an example of how to use Jekyll to create blog posts.</p>

<h2>Subheading</h2>

<p>You can add as many headings and paragraphs as you like.</p>

<p>Here's an example of a list:</p>

<ul>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<p>Here are some tags for this post:</p>
<ul>
{% for tag in page.tags %}
  <li><a href="/tags/{{ tag }}/">{{ tag }}</a></li>
{% endfor %}
</ul>

<p><a href="/">Back to Home</a></p>
