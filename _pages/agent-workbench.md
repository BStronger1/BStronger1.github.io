---
lang: en
translation_url: /zh/projects/agent-workbench/
layout: single
title: "Agent Workbench"
permalink: /projects/agent-workbench/
author_profile: true
---

A personal AI workspace centered on LLM application generation: project memory augments model context, browser validation feeds bounded code-repair attempts, and run records retain versions, latency and token usage.

[GitHub repository](https://github.com/BStronger1/agent-workbench) · [Architecture](https://github.com/BStronger1/agent-workbench/blob/main/docs/ARCHITECTURE.md) · [Verification record](https://github.com/BStronger1/agent-workbench/blob/main/docs/EVALUATION.md)

![Agent Workbench interface](/images/agent-workbench.png)

### What it does

- **Application studio:** self-contained HTML generation, explicit acceptance requirements, browser interaction checks, bounded repair, saved attempts and version selection.
- **Project memory:** versioned constraints, decisions and lessons; superseded entries become inactive; retrieved context retains source IDs.
- **Project knowledge:** text/Markdown ingestion with lexical retrieval and paragraph-level references.
- **Reporting:** Markdown development reports derived from recorded sources and run evidence.
- **Evaluation:** separate demo/live run labels, latency and usage records, and reproducible contract fixtures.
- **Model settings:** users supply their own endpoint, model name and API key; configurations are encrypted per browser workspace, with connection testing, enable/disable and removal controls.

### Engineering choices

The AI workflow retrieves project context, calls a Chat Completions-compatible model, checks generated HTML, and runs Playwright text/interaction acceptance checks. Failures and previous code feed the next model attempt, with at most three repairs and a pre-call token-budget check. A two-worker executor has twelve queue slots. Document retrieval and report assembly currently use deterministic logic rather than model-generated answers.

Java 21 and Spring Boot serve the API and packaged Vue/TypeScript frontend. Per-project snapshots persist state without external databases. Generated artifacts remain self-contained HTML: the service does not install or execute model-generated npm projects. Browser preview uses an isolated iframe and content security policy; the verification worker blocks external requests.

The private deployment supports HTTPS with a dedicated local CA. Certificate-chain and IP-identity verification, browser workflow checks and migration of existing workspace cookies to Secure cookies have been tested. Client devices must explicitly trust the local CA before normal access.

### What has been verified

25 backend tests cover persistence, ownership isolation, memory updates, failure handling, repair limits, budget checks, encrypted model configuration and request routing. Browser checks cover the generation workflow, retrieval, reporting and model settings. In 36 deterministic demo cases, 18 passed initially and 18 intentionally injected button failures passed after a predefined repair. This validates the workflow on those fixtures, **not** real-model quality or the effectiveness of memory retrieval.

The live-model HTTP adapter is implemented; actual provider compatibility, generation quality and model comparisons remain unverified until API configuration is supplied.

### Personal project

I developed Agent Workbench to bring application building, project knowledge and development reporting into one workspace. The implementation includes memory versioning, acceptance contracts, bounded repair, browser verification, user-configured models, evidence reporting and deployment tooling.
