---
layout: page
title: Tools
permalink: /tools/
---

{% assign tools_by_category = site.tools | sort: 'category' | group_by: 'category' %}
{% for category in tools_by_category %}
  <section class="tool-category">
    <h2>{{ category.name | default: 'Other' }}</h2>
    <ul class="content-list">
      {% assign sorted_tools = category.items | sort: 'title' %}
      {% for tool in sorted_tools %}
        {% assign usage_count = 0 %}
        {% for post in site.posts %}
          {% if post.tools contains tool.title %}{% assign usage_count = usage_count | plus: 1 %}{% endif %}
        {% endfor %}
        <li>
          <a href="{{ tool.url | relative_url }}">{{ tool.title }}</a>
          <span class="usage-count">Used in {{ usage_count }} {% if usage_count == 1 %}writeup{% else %}writeups{% endif %}</span>
        </li>
      {% endfor %}
    </ul>
  </section>
{% else %}
  <p class="empty">No tools yet.</p>
{% endfor %}
