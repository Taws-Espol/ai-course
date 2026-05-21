---
title: Getting Started
nav_order: 1
links:
  - label: Setup checklist
    url: "#"
---

This tutorial walks through the first local setup steps for working on the course website.

## Prerequisites

Before starting, confirm these tools are available:

```bash
git --version
ruby --version
bundle --version
```

If `bundle` is not installed, install Bundler for your Ruby environment before continuing.

## Clone The Repository

Clone the project and move into the site directory.

```bash
git clone https://github.com/taws-espol/ai-course.git
cd ai-course
```

Install the Ruby dependencies:

```bash
bundle install
```

## Run The Site Locally

Start the Jekyll development server.

```bash
bundle exec jekyll serve
```

Open the local URL shown in the terminal. Because this site is deployed under `/ai-course`, local pages may be served from:

```text
http://127.0.0.1:4000/ai-course/
```

If you edit `_config.yml`, stop and restart the server.

## Make A Test Edit

Edit a Markdown file, save it, and refresh the browser.

Good files for a first edit:

- `calendar.md`
- `resources.md`
- `_lectures/course-introduction.md`

## Troubleshooting

| Problem | What To Try |
| --- | --- |
| Page still shows old content | Restart `bundle exec jekyll serve`. |
| Link works locally but not deployed | Check whether the link includes `relative_url`. |
| Build cannot download theme | Confirm network access to GitHub. |
| Markdown renders strangely | Check blank lines around headings, lists, and tables. |
