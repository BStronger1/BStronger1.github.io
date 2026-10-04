---
layout: single
title: "Agent Workbench"
permalink: /projects/agent-workbench/
author_profile: true
---

A personal AI workspace for turning requirements into verifiable artifacts, with explicit project memory and source-grounded reporting.

[GitHub repository](https://github.com/BStronger1/agent-workbench) · [Architecture](https://github.com/BStronger1/agent-workbench/blob/main/docs/ARCHITECTURE.md) · [Verification record](https://github.com/BStronger1/agent-workbench/blob/main/docs/EVALUATION.md)

![Agent Workbench interface](/images/agent-workbench.png)

### What it does

- **Application studio:** self-contained HTML generation, explicit acceptance requirements, browser interaction checks, bounded repair, saved attempts and version selection.
- **Project memory:** versioned constraints, decisions and lessons; superseded entries become inactive; retrieved context retains source IDs.
- **Project knowledge:** text/Markdown ingestion with lexical retrieval and paragraph-level references.
- **Reporting:** Markdown development reports derived from recorded sources and run evidence.
- **Evaluation:** separate demo/live run labels, latency and usage records, and reproducible contract fixtures.

### Engineering choices

Java 21 and Spring Boot serve the API and packaged Vue/TypeScript frontend. Per-project snapshots persist state without external databases. Generated artifacts remain self-contained HTML: the service does not install or execute model-generated npm projects. Browser preview uses an isolated iframe and content security policy; the verification worker blocks external requests.

### What has been verified

13 backend tests and a browser end-to-end test cover persistence, ownership isolation, memory updates, failure handling, repair limits, budget checks, document retrieval and reporting. In 36 deterministic demo cases, 18 passed initially and 18 intentionally injected button failures passed after a predefined repair. This validates the workflow on those fixtures, **not** real-model quality or the effectiveness of memory retrieval.

The live-model HTTP adapter is implemented; actual provider compatibility, generation quality and model comparisons remain unverified until API configuration is supplied.

### Provenance and contribution

The project grew from studying [yu-ai-code-mother](https://github.com/liyupi/yu-ai-code-mother). The public repository contains a newly authored independent workbench module rather than a copy of the upstream implementation. Development was AI-assisted. Contributions include the runnable no-key workflow, memory versioning, acceptance contracts, bounded repair, browser verification, evidence reporting and deployment tooling.
