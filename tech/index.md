---
layout: main
main: true
title: tech
---


<div class="row">
    <div class="sidebar">

    </div>
    <div class="right-contents">
        <div class="category-container">
            <h3>Category</h3>
            {% include tags.html %}
        </div>

        <div class="columns">
            <ul class="catalogue">
                {% assign sorted = site.pages | sort: 'date' | reverse | where: 'type', 'tech' %}
                {% for page in sorted %}
                {% include post-list.html %}
                {% endfor %}
            </ul>
        </div>
    </div>
</div>
