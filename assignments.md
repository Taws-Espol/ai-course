---
layout: page
title: Assignments
nav_order: 3
has_children: true
description: Course assignments.
---

# Assignments

{% assign assignments = site.assignments | sort: 'nav_order' %}
<div class="content-list">
{% for assignment in assignments %}
  <article class="content-list-item">
    <h2 class="fs-4"><a href="{{ assignment.url | relative_url }}">{{ assignment.title }}</a></h2>
    <p>{{ assignment.content | strip_html | truncate: 140 }}</p>
  </article>
{% endfor %}
</div>
