---
title: Course Introduction
nav_order: 1
parent: Lectures
subtopics:
  - Course goals
  - Website workflow
  - Development environment
resources:
  - label: Slides
    url: "#"
  - label: Notes
    url: "#"
---

This lecture introduces the course structure, expectations, and the tools we will use throughout the term. By the end, students should understand how the course is organized and how to start working locally.

## 1.1 Course Goals

The course is designed around building practical AI systems, not only reading about them. Each week combines a conceptual topic with a small implementation task so students can connect ideas to working code.

By the end of the course, students should be able to:

- Explain core AI and machine learning concepts in plain language.
- Build small applications that use AI models responsibly.
- Evaluate tradeoffs in model behavior, data quality, and user experience.
- Document technical decisions clearly enough for another developer to continue the work.

## 1.2 How The Website Is Organized

The website has four main sections:

- **Calendar**: weekly lecture and assignment links.
- **Lectures**: notes, examples, references, and recordings.
- **Assignments**: prompts, requirements, submission details, and grading notes.
- **Tutorials**: guided setup and walkthrough material.

Lecture pages can contain regular Markdown content, including code blocks, tables, lists, and section headings. Section headings are useful because they create anchors that can be linked from the calendar or from other pages.

## 1.3 Development Environment

Students should have a working shell, Git, Ruby, and a code editor installed before starting the first assignment.

```bash
git --version
ruby --version
bundle --version
```

If a command is missing, record the error message and bring it to office hours. Environment issues are easier to debug when the exact command and output are available.

## Discussion Questions

- What makes an AI feature useful rather than just impressive?
- Where can model output fail even when the model appears confident?
- What should a course website make easy for students to find every week?
