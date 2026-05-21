---
layout: page
title: Calendar
nav_order: 1
description: Weekly course calendar.
---

# Calendar

{% capture course_intro_url %}{% link _lectures/course-introduction.md %}{% endcapture %}
{% capture workflow_url %}{% link _lectures/development-workflow.md %}{% endcapture %}
{% capture assignment_1_url %}{% link _assignments/assignment-1.md %}{% endcapture %}

| Week | Lecture | Assignment |
| --- | --- | --- |
| Week 1 | [Course Introduction]({{ course_intro_url | relative_url }}) | [Assignment 1]({{ assignment_1_url | relative_url }}) |
| Week 2 | [Development Workflow]({{ workflow_url | relative_url }}) | [Assignment 1 due]({{ assignment_1_url | relative_url }}) |
