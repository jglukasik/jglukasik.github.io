---
title: Projects
layout: default
---

# Here are some projects I've worked on:

<ul>
  {% for post in site.tags.project %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a> - {{ post.description }}
  </li>
  {% endfor %}
</ul>
