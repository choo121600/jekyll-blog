---
layout: main
main: true
title: tech
---



<div class="title">
    <h2 class="title-text">tech 게시물</h2>
</div>
{% include tags.html %}
<div class="contents">
    <table class="catalouge">
        <tr>
            {% assign sorted = site.pages | sort: 'date' | reverse | where: 'type', 'tech' %}
            {% for page in sorted limit:3 %}
            {% include post-card.html %}
            {% endfor %}
        </tr>
    </table>
</div>



<div class="columns">
    <ul class="catalogue">
        {% assign sorted = site.pages | sort: 'date' | reverse | where: 'type', 'tech' %}
        {% for page in sorted %}
        {% include post-list.html %}
        {% endfor %}
    </ul>
</div>