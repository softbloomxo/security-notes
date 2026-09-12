---
layout: default
title: security notes
---

<section class="home-hero">
  <p class="terminal-prompt">$ cd ~/security-notes</p>
  <h1>security notes</h1>
  <p class="intro">Security / CTF / Programming</p>
</section>

<section class="recent-writeups">
  <h2>Recent Writeups</h2>

  <ul class="content-list">
  {% for post in site.posts limit: 5 %}
    <li><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%Y-%m-%d' }}</time> <a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
  {% else %}
    <li class="empty">No writeups yet.</li>
  {% endfor %}
  </ul>

  <a class="text-link" href="{{ '/writeups/' | relative_url }}">View all writeups <span aria-hidden="true">→</span></a>
</section>
