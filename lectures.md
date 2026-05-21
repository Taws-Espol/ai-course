---
layout: page
title: Lectures
nav_order: 2
has_children: true
description: Lecture topics and supporting materials.
---

# Lectures

{% assign lectures = site.lectures | sort: 'nav_order' %}
<div class="content-list">
{% for lecture in lectures %}
  <article class="content-list-item">
    <h2 class="fs-4"><a href="{{ lecture.url | relative_url }}">{{ lecture.title }}</a></h2>
    <p>
    {% if lecture.subtopics %}
      {{ lecture.subtopics | join: ', ' }}
    {% else %}
      {{ lecture.content | strip_html | truncate: 140 }}
    {% endif %}
    </p>
  </article>
{% endfor %}
</div>
