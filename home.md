---
layout: page
title: Home
permalink: /home/
---

<div class="home-page-content">

<p>Some people have one hobby, interest, or passion, and get really good at that one thing. I prefer to dip my toes into everything, and be not very good at any of them. This is a website dedicated to documenting that process.</p>

<h1>Latest post</h1>

{% assign latest_post = site.posts.first %}

<article class="post">
  <h3>{{ latest_post.title }}</h3>
  <p class="post-meta">{{ latest_post.date | date: "%b %-d, %Y" }}</p>
  
  {{ latest_post.content }}
</article>

<a href="/posts/">See all posts →</a>

</div>