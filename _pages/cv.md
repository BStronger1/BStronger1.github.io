---
lang: en
translation_url: /zh/cv/
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* M.S. in Cognitive Neuroscience, Beijing Normal University, State Key Laboratory of Cognitive Neuroscience and Learning (in progress)
* B.S., 20XX

Research Interests
======
* Cognitive neuroscience of learning and memory
* Memory-augmented large language models
* Retrieval and knowledge organization

Projects
======
### [Recall Agent — Personal AI with User-Controlled Memory]({{ '/projects/recall-agent/' | relative_url }})
**Personal project · October 2026 · AI-assisted development**

Java 21 · Spring Boot · Vue 3 · Chat Completions-compatible APIs

* Built a memory-assisted conversation workflow combining recent messages, explicitly saved preferences/facts/project context, and retrieved knowledge; exposed recalled memory and source references alongside answers.
* Added self-service registration, persistent login and account-bound workspaces, with cross-device access and a binding flow for existing browser workspaces. New accounts use their own model API credentials, encrypted at rest with AES-GCM.
* Implemented local keyword retrieval and adapters for Dify / RAGFlow; account workspaces currently use isolated local knowledge. External adapters have fixture-based tests and require separate live-service validation.
* Deployed the combined frontend/backend on a private Linux server with persistent storage and process supervision; passed 19 backend tests and live-model checks for memory recall, account login, credential isolation and restart persistence.

[Source code](https://github.com/BStronger1/recall-agent) · [Interactive demo](https://bstronger1.github.io/recall-agent/) · [Implementation and verification]({{ '/projects/recall-agent/' | relative_url }})

### [AI PPT生成 — AI Presentation Generator]({{ '/projects/ai-ppt-generator/' | relative_url }})
**AI Product · October 2026**

React / TypeScript · FastAPI · PostgreSQL · Redis / ARQ · LangGraph · python-pptx

* Added account-specific model selection, API key encryption, model discovery and connection testing, with isolated credentials across users.
* Implemented six audience presets and AI narrative planning informed by cognitive-load, multimedia-learning, and elaboration principles; carried the plan into page roles, visual structure, timing, and speaker notes.
* Added outline-level source excerpts, reference validation, and invalidation of citations after edits; exposed evidence for review in the editor and preserved it in PPTX speaker notes.
* Deployed the application, worker, database, and queue in an isolated Linux user environment with persistent storage and process supervision; verified a six-slide real-model generation/export workflow and data retention after service restarts.

Live access is restricted to the authorized internal network; a [project walkthrough and sample PPTX]({{ '/projects/ai-ppt-generator/' | relative_url }}) are publicly available.

### Agent Workbench — Memory-Augmented AI App Generation and Browser-Validated Repair
**Personal project · October 2026**

[Source code](https://github.com/BStronger1/agent-workbench) · [Project overview](/projects/agent-workbench/)

Java 21 · Spring Boot · Vue 3 / TypeScript · Playwright · Chat Completions-compatible APIs

* Implemented an LLM application-generation workflow that assembles requirements, project memory and acceptance criteria into model context, validates generated HTML with Playwright, and feeds failures and previous code into up to three repair attempts with version rollback.
* Built versioned constraints, decisions and lessons with Chinese-bigram/keyword retrieval, source references and no-memory, recent-request and retrieved-memory context strategies.
* Added user-configured models and AES-256-GCM encrypted API keys with browser-workspace isolation; bounded the task queue and token budget while recording latency, attempts and provider-reported usage.
* Verified 25 backend tests, browser end-to-end checks and 36 deterministic demo cases, and deployed private Linux HTTPS access. The live adapter and evaluation runner are implemented; actual generation, repair quality and memory benefits await API testing.

Skills
======
* Programming: Python
* Machine learning / deep learning
* Data analysis

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Service and outreach
======
* (Add your academic service, reviewing, or volunteering here.)
