---
layout: home
permalink: /
---

<div class="welcome-section home-section">
  <h1>Welcome</h1>
  <p>Some people have one hobby, interest, or passion, and get really good at that one thing. I prefer to dip my toes into everything, and be not very good at any of them. This is a website dedicated to documenting that process.</p>
</div>

<div class="latest-post-section home-section">
  <h2>Latest post</h2>
  {% if site.posts.size > 0 %}
    {% assign latest_post = site.posts.first %}
    <h3><a href="{{ latest_post.url | relative_url }}">{{ latest_post.title }}</a></h3>
    <p class="post-meta">{{ latest_post.date | date: "%b %-d, %Y" }}</p>
    <div class="post-excerpt">
      {{ latest_post.excerpt | strip_html | truncatewords: 60, "..." }}
    </div>
    <a href="{{ latest_post.url | relative_url }}">Read more →</a>
  {% endif %}
</div>