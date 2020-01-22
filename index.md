---
title: The Finch
---
<div id="main-wide">
  
  {% for post in site.posts limit: 1 %}
    {% include post-feature.html %}
  {% endfor %}

  
  {% for post in site.posts offset: 1 %}
    {% include post-preview.html %}
  {% endfor %}

</div>