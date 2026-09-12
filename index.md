---
layout: page
title: security notes
---

<p class="intro">Security / CTF / Programming</p>

## Recent Writeups

<ul class="content-list">
{% for post in site.posts limit: 5 %}
  <li><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%Y-%m-%d' }}</time> <a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
{% else %}
  <li class="empty">No writeups yet.</li>
{% endfor %}
</ul>

[View all writeups]({{ '/writeups/' | relative_url }})
