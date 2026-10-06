---
lang: en
translation_url: /zh/projects/
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

## [Recall Agent — Personal AI with User-Controlled Memory]({{ '/projects/recall-agent/' | relative_url }})

Manage long-term preferences, facts and project context, combine them with recent conversations and retrieved knowledge, and inspect the evidence used in each answer. Self-service accounts keep memory and personal model settings available across devices.

**Stack:** Java 21, Spring Boot, Vue 3, Vite, Chat Completions-compatible APIs.

Verified 19 backend tests and live-model checks for memory recall, personal API configuration, login across devices and persistence after application restarts. The public demo uses sample content; the full service is available on an authorized campus/VPN network.

[Project details and verification]({{ '/projects/recall-agent/' | relative_url }}) · [Interactive demo](https://bstronger1.github.io/recall-agent/) · [Source code](https://github.com/BStronger1/recall-agent)

[![Recall Agent demo workspace with sample memory and context panels]({{ '/images/recall-agent.png' | relative_url }})]({{ '/projects/recall-agent/' | relative_url }})

## [Agent Workbench — Project Memory & Browser-Validated Repair]({{ '/projects/agent-workbench/' | relative_url }})

Connect requirements and retrieved memory to LLM-generated HTML, browser acceptance checks and error-feedback repair. Includes three context strategies, token budgets, run evidence and encrypted user model configuration.

**Stack:** Java 21, Spring Boot, Vue 3, TypeScript, Playwright.

Verified 25 backend tests, browser end-to-end checks and 36 deterministic demo cases. Live-model integration is implemented but not yet API-validated; demo results are workflow checks, not model performance measurements.

[View project and evidence]({{ '/projects/agent-workbench/' | relative_url }}) · [Source code](https://github.com/BStronger1/agent-workbench)

[![Agent Workbench interface]({{ '/images/agent-workbench.png' | relative_url }})]({{ '/projects/agent-workbench/' | relative_url }})

## [AI PPT生成 — AI Presentation Generator]({{ '/projects/ai-ppt-generator/' | relative_url }})

Turn project materials into editable presentation slides and review the source excerpts behind outline claims. The application includes a project-defense workflow, evidence review, and deployment on a private Linux server.

**Stack:** React / TypeScript, FastAPI, PostgreSQL, Redis / ARQ, LangGraph, python-pptx.

[View project and validation results]({{ '/projects/ai-ppt-generator/' | relative_url }}) · [Download example PPTX]({{ '/files/ai-ppt-generator-demo.pptx' | relative_url }})

[![AI PPT生成 editor with source excerpts and missing-evidence indicators]({{ '/images/ai-ppt-generator-editor.jpg' | relative_url }})]({{ '/projects/ai-ppt-generator/' | relative_url }})
