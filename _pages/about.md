---
lang: en
translation_url: /zh/
permalink: /
title: "Yangbin Zou"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a Master's student at the [State Key Laboratory of Cognitive Neuroscience and Learning](https://brain.bnu.edu.cn/), [Beijing Normal University](https://www.bnu.edu.cn/).

My research interests lie at the intersection of cognitive neuroscience and machine learning, with a particular focus on memory. I am interested in how principles of human memory can inform the design of memory systems for large language models, and vice versa.

Research Interests
======
* Cognitive neuroscience of learning and memory
* Memory-augmented large language models
* Retrieval and knowledge organization

Selected Projects
======
**[Recall Agent — Personal AI with User-Controlled Memory]({{ '/projects/recall-agent/' | relative_url }})** combines editable long-term memory, recent conversation history and source-referenced knowledge retrieval. Users can register, bring their own model API and access the same workspace across devices. The private deployment has passed real-model memory-recall and restart-persistence checks. [Interactive demo](https://bstronger1.github.io/recall-agent/) · [Source code](https://github.com/BStronger1/recall-agent)

**[AI PPT生成 — AI Presentation Generator]({{ '/projects/ai-ppt-generator/' | relative_url }})** converts project materials into editable presentation slides with outline-level source excerpts. The application includes a project-defense workflow, evidence review, and persistent deployment on a private Linux server. A screenshot and downloadable example are available on the project page.

**[Agent Workbench](https://github.com/BStronger1/agent-workbench)** — A personal AI workspace connecting project memory, self-contained application generation, browser interaction checks and bounded repair. Includes source-grounded document retrieval, development reports and user-configured models with encrypted API-key storage. Built with Python/FastAPI, LangChain, LangGraph, pgvector, Java/Spring Boot, Vue/TypeScript and Playwright. [Project details](/projects/agent-workbench/)

LangChain/LangGraph role workflows, checkpoint recovery, pgvector hybrid retrieval and cited RAG; verified with 29 Java tests, 20 Python tests and browser checks. The upgrade is deployed on private HTTPS. Six paired real-model tasks with DMXAPI-deepseek-v4-flash made 15 calls with 4/6 accepted, plus 2/2 cited RAG probes passed. All failures are retained; these are development scenarios, not a general benchmark.

The failed checklist scenario was fixed and passed targeted single-role and multi-role reruns (2/2) with the same model and frozen contracts. Earlier full-evaluation and intermediate failures are preserved. This fix is verified on the full local service chain; server synchronization awaits SSH recovery. [Fix report](https://github.com/BStronger1/agent-workbench/blob/main/docs/CHECKLIST-REGRESSION.md)

News
======
* **October 2026:** Added Recall Agent to my portfolio, with account-bound memory, encrypted personal model credentials and a verified live-model deployment on a private Linux server.
* **October 2026:** Added AI PPT生成 to my project portfolio after validating material upload, real-model generation, editable PPTX export, and persistence across service restarts.

Contact
======
Feel free to reach out via email (see the sidebar) if you would like to discuss research or potential collaborations.
