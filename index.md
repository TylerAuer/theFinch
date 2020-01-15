---
layout: feature-list
title: Front Page
feat-img: assets/images/dark-girl-looking-up.jpg
---

<ul>
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p>By: {{ post.authors }}</p>
      <p>{{ post.snippet }}</p>
    </li>
  {% endfor %}
</ul>
