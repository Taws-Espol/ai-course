---
title: Development Workflow
nav_order: 100
parent: Lectures
subtopics:
  - Version control basics
  - Local development loop
  - Submitting work
resources:
  - label: Slides
    url: "#"
---

This lecture covers the development loop used for course work: make a small change, run the project, inspect the result, and commit a clear checkpoint.

## 2.1 Version Control Basics

Use Git to keep a history of meaningful changes. A good commit captures one idea: a page update, a bug fix, a new component, or a small refactor.

```bash
git status
git diff
git add .
git commit -m "Add calendar table"
```

Before committing, read your diff. The diff is the best way to catch accidental edits, generated files, or unrelated changes.

## 2.2 Local Development Loop

For this Jekyll site, the normal local loop is:

```bash
bundle exec jekyll serve
```

Then open the local site in the browser and refresh after editing Markdown, layout, or Sass files. If `_config.yml` changes, restart the server because Jekyll does not reload configuration automatically.

## 2.3 Debugging Links

Broken links are common when deploying to GitHub Pages with a `baseurl`. Prefer `relative_url` when generating internal links with Liquid.

```liquid
{{ page.url | relative_url }}
```

For Markdown links to collection documents, capture the generated path first and then pass it through `relative_url`.

```liquid
{% raw %}{% capture lecture_url %}{% link _lectures/course-introduction.md %}{% endcapture %}
[Course Introduction]({{ lecture_url | relative_url }}){% endraw %}
```

## 2.4 Submitting Work

Before submitting an assignment, make sure the project builds, links work from the deployed path, and the relevant pages contain enough explanation for someone else to review your work.

| Check | What to Verify |
| --- | --- |
| Build | The site generates without errors. |
| Links | Internal links include the correct base path. |
| Content | The page explains the goal, steps, and result. |
| Diff | Only intentional source files changed. |
