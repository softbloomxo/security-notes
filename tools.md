---
layout: page
title: Tools
permalink: /tools/
---

<ul class="content-list">
{% assign sorted_tools = site.tools | sort: 'title' %}
{% for tool in sorted_tools %}
  <li><a href="{{ tool.url | relative_url }}">{{ tool.title }}</a>{% if tool.category %} <span class="meta">- {{ tool.category | downcase }}</span>{% endif %}</li>
{% else %}
  <li class="empty">No tools yet.</li>
{% endfor %}
</ul>
