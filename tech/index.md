---
layout: main
main: true
title: tech
---



{% include tags.html %}

<div class="columns">
    <ul class="catalogue">
        {% assign sorted = site.pages | sort: 'date' | reverse | where: 'type', 'tech' %}
        {% for page in sorted %}
        {% include post-list.html %}
        {% endfor %}
    </ul>
</div>