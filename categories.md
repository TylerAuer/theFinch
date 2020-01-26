---
title: Categories
---

<div id="main-wide" class="text-center">

    {% for category in site.category %}
        <h2>
            <a href="{{ category.url }}.html">
                {{ category.title }}
            </a>
        </h2>
    {% endfor %}

</div>
