---
layout: page
title: Writeups
permalink: /writeups/
---

<ul class="content-list">
{% for post in site.posts %}
  <li>
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: '%Y-%m-%d' }}</time>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    {% if post.tags and post.tags.size > 0 %}
      <ul class="tag-list" aria-label="Tags">{% for tag in post.tags %}<li>{{ tag }}</li>{% endfor %}</ul>
    {% endif %}
  </li>
{% else %}
  <li class="empty">No writeups yet.</li>
{% endfor %}
</ul>
