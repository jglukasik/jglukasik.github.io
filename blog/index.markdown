---
title: Blog
layout: default
---

# Here are some blog posts I've written:

<ul>
  {% for post in site.tags.blog %}
  <li>
    <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
  {% endfor %}
</ul>
