---
layout: feature-list
title: Front Post
feat-img: assets/images/dark-girl-looking-up.jpg
---

<ul>
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p>By: 
          {% assign authorCount = post.authors | size %}
            {% if authorCount == 0 %}
              Anonymous
            {% elsif authorCount == 1 %}
              {{ post.authors | first }}
            {% else %}
              {% for author in post.authors %}
                {% if forloop.first %}
                  {{ author }}, 
                {% elsif forloop.last %}
                  and {{ author }}
                {% else %}
                  {{ author }}, 
                {% endif %}
              {% endfor %}
            {% endif %}
      </p>
      <p>{{ post.snippet }}</p>
    </li>
  {% endfor %}
</ul>
