---
layout: default
title: Contributors
---
{% include header.html%}

<div id="main-wide" class="text-center">

<ul>
    {% for contributor in site.contributors %}
        <h3>
            <a href="{{ contributor.url }}">{{ contributor.title }}</a>
        </h3>
    {% endfor %}
</ul>

</div>