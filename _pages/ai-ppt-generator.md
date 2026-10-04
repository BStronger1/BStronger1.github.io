---
layout: single
title: "AI PPT生成 — AI Presentation Generator"
permalink: /projects/ai-ppt-generator/
author_profile: true
excerpt: "Audience-aware AI presentation planning, outline evidence review, and editable PPTX export."
---

**AI Product · October 2026**

AI PPT生成 turns project materials into an editable presentation. It first plans how to tell the story for the intended audience, then generates page objectives, evidence, visual structure, and a native PPTX. Academic presentations can lead with a research question; management presentations can lead with a decision; introductory teaching can begin with a familiar situation.

**Stack:** React / TypeScript · FastAPI · PostgreSQL · Redis / ARQ · LangGraph · python-pptx

## Workflow

Choose the audience, prior knowledge, duration, and goal → upload or paste materials → review the AI narrative plan and outline evidence → generate and edit slides → export an editable PPTX with speaker notes.

![Audience presets and presentation goals]({{ '/images/ai-ppt-audience.jpg' | relative_url }})

![AI PPT生成 editor showing source excerpts and a missing-evidence indicator]({{ '/images/ai-ppt-generator-editor.jpg' | relative_url }})

The screenshot shows a fictional validation case, including a claim marked as needing additional evidence.

## Product features

* **Personal model settings:** Choose an OpenAI-compatible model, retrieve the available-model list, test connectivity, and use an account-specific API key stored with encryption. The selected model is used for outlines, slides, AI edits, and relayout.
* **Audience-aware narrative:** Six presets cover academic review, management, technical peers, investment/business review, introductory teaching, and custom audiences. Prior knowledge and user instructions take precedence over preset assumptions.
* **Explainable planning:** Show the proposed opening, narrative stages, closing action, rationale, and assumptions before slide generation. Use cognitive-load, multimedia-learning, and elaboration principles as design references; visibly label preset fallback if AI planning fails.
* **Page design and delivery:** Assign page roles, transitions, and a speaking-time budget. Use comparison, process, evidence, or claim layouts according to the information; preserve purposeful whitespace and export narrative guidance in speaker notes.
* **Outline evidence review:** Attach source references and excerpts to individual outline points. Validate that excerpts exist in the supplied materials; mark invalid references and edited claims for review.
* **Evidence in the editing workflow:** Add source inspection and supplementary-material entry points, and preserve outline references in exported speaker notes.
* **More conservative handling of missing material:** Allow short content and explicit evidence gaps in the defense scenario, instead of automatically expanding sparse content to meet density targets.
* **Deployment and verification:** Run the API, worker, PostgreSQL, and Redis in an isolated Linux user environment with persistent storage, process supervision, and a configured startup entry.

## What was verified

On **October 4, 2026**, a server acceptance run uploaded a fictional text file, generated a six-page outline and six slides using the configured model API, and exported a **52,400-byte PPTX**. The export was read back to verify editable text and outline-source notes on every slide.

After restarting the application's four services, all six slide records remained ready and the uploaded file's SHA-256 matched the original. The startup entry was installed and its launcher tested; the shared server itself was not rebooted.

The latest local backend regression suite reported **416 passed, 3 skipped**. Two additional real-model runs used the same fictional material for management and introductory teaching audiences: both produced an AI narrative plan, a 300-second allocation, and six editable slides. The management opening proposed a decision; the teaching opening used a lost-wallet scenario and concluded with an exercise. These checks cover software behavior, not a measured reduction in hallucinations or a user productivity gain.

## Example and access

[Download the server-generated example PPTX]({{ '/files/ai-ppt-generator-demo.pptx' | relative_url }})

Compare the same fictional material: [management narrative]({{ '/files/ai-ppt-management.pptx' | relative_url }}) · [introductory teaching narrative]({{ '/files/ai-ppt-teaching.pptx' | relative_url }}).

The examples use a **fictional campus lost-and-found project** and preserve model output for inspection. They are not evidence of real users or project performance. Content still requires review: for example, the management sample adds unsupported two-week timelines and implementation assumptions. Quantity checks and evidence indicators help surface gaps but do not establish factual accuracy.

The application is deployed on a **private Linux server**. Live access requires authorized internal-network access; there is no public demo endpoint. The screenshot and sample above can be viewed without server access. The application's source has not yet been published as a separate GitHub repository.

## Boundaries

Evidence is attached to **outline points**, not every generated sentence. Excerpt matching only checks that text exists in the source; it does not establish that the source supports the claim. Generated body text and manual edits still require review. This version does not implement OCR, retrieval-augmented generation, or automated semantic fact-checking.

Audience presets are editable product hypotheses, not psychological profiling. No audience study has validated improvements in comprehension, recall, or persuasion.
