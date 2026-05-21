---
layout: page
title: Tutorials
nav_order: 4
has_children: true
description: Course tutorials.
---

# Tutorials

{% assign tutorials = site.tutorials | sort: 'nav_order' %}
<div class="content-list">
{% for tutorial in tutorials %}
  <article class="content-list-item">
    <h2 class="fs-4"><a href="{{ tutorial.url | relative_url }}">{{ tutorial.title }}</a></h2>
    <p>{{ tutorial.content | strip_html | truncate: 140 }}</p>
  </article>
{% endfor %}
</div>
