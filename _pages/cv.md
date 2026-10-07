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

### Agent Workbench — AI application development with LangGraph and RAG
**Personal project · October 2026**

[Source](https://github.com/BStronger1/agent-workbench) · [Project overview](/projects/agent-workbench/)

Python / FastAPI · LangChain · LangGraph · PostgreSQL / pgvector · Embedding / RAG · Playwright · Java / Spring Boot · Vue / TypeScript

* Built a LangChain/LangGraph workflow for planning, code generation, browser acceptance, independent review and bounded repair, with single-role and multi-role modes, plan approval and persistent checkpoints. A call journal reuses completed replies and blocks automatic replay of uncertain requests.
* Implemented RAG with local multilingual embeddings and pgvector, combining Chinese-bigram/keyword and vector retrieval through reciprocal rank fusion, workspace/project filtering, active-memory synchronization and source-ID validation.
* Developed structured Playwright contracts for checkbox, input, click and result assertions; froze acceptance criteria before generation and fed browser failures and reviewer feedback into the coding role while preserving artifacts and screenshots.
* Added user-configured models, AES-256-GCM encrypted credentials, bounded queues, token-budget prechecks and per-role usage records while preserving the Java baseline and demo workflow.
* Verified 29 Java and 20 Python tests plus real pgvector/embedding and browser integration. Evaluated six paired single/multi-role tasks with DMXAPI-deepseek-v4-flash (15 calls, 4/6 accepted) and two cited RAG probes (2/2 passed), preserving failures.

Deployed on private HTTPS. These authored development scenarios do not establish multi-agent quality gains; no fine-tuning has been performed. [Verification report](https://github.com/BStronger1/agent-workbench/blob/main/docs/GRAPH-LIVE-RESULTS.md)

The failed checklist scenario was fixed and passed targeted single-role and multi-role reruns (2/2) with the same model and frozen contracts. Earlier full-evaluation and intermediate failures are preserved. This fix is verified on the full local service chain; server synchronization awaits SSH recovery. [Fix report](https://github.com/BStronger1/agent-workbench/blob/main/docs/CHECKLIST-REGRESSION.md)

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
