---
layout: single
title: "AI PPT生成 — AI Presentation Generator"
permalink: /projects/ai-ppt-generator/
author_profile: true
excerpt: "An AI-assisted project-defense presentation tool with outline-level evidence review and editable PPTX export."
---

**AI Product · October 2026**

AI PPT生成 turns project materials into a presentation that can be edited and exported as a native PPTX. It focuses on project-defense presentations: explaining the problem, solution, implementation, results, and remaining limitations without treating planned work as completed work.

**Stack:** React / TypeScript · FastAPI · PostgreSQL · Redis / ARQ · LangGraph · python-pptx

## Workflow

Set the audience, duration, and presentation focus → upload or paste materials → review the outline and its evidence → generate and edit slides → export an editable PPTX.

![AI PPT生成 editor showing source excerpts and a missing-evidence indicator]({{ '/images/ai-ppt-generator-editor.jpg' | relative_url }})

The screenshot shows a fictional validation case, including a claim marked as needing additional evidence.

## Product features

* **Personal model settings:** Choose an OpenAI-compatible model, retrieve the available-model list, test connectivity, and use an account-specific API key stored with encryption. The selected model is used for outlines, slides, AI edits, and relayout.
* **Project-defense brief:** Store the presentation scenario, duration, and focus separately from source material, then pass them into outline and slide generation.
* **Outline evidence review:** Attach source references and excerpts to individual outline points. Validate that excerpts exist in the supplied materials; mark invalid references and edited claims for review.
* **Evidence in the editing workflow:** Add source inspection and supplementary-material entry points, and preserve outline references in exported speaker notes.
* **More conservative handling of missing material:** Allow short content and explicit evidence gaps in the defense scenario, instead of automatically expanding sparse content to meet density targets.
* **Deployment and verification:** Run the API, worker, PostgreSQL, and Redis in an isolated Linux user environment with persistent storage, process supervision, and a configured startup entry.

## What was verified

On **October 4, 2026**, a server acceptance run uploaded a fictional text file, generated a six-page outline and six slides using the configured model API, and exported a **52,400-byte PPTX**. The export was read back to verify editable text and outline-source notes on every slide.

After restarting the application's four services, all six slide records remained ready and the uploaded file's SHA-256 matched the original. The startup entry was installed and its launcher tested; the shared server itself was not rebooted.

The local backend regression suite reported **392 passed, 3 skipped**. These checks cover software behavior, not a measured reduction in hallucinations or a user productivity gain.

## Example and access

[Download the server-generated example PPTX]({{ '/files/ai-ppt-generator-demo.pptx' | relative_url }})

The example uses a **fictional campus lost-and-found project** and preserves the model's output for inspection. It is not evidence of real users or project performance. Its content-quality report still contained warnings about placeholder language and incomplete evidence coverage.

The application is deployed on a **private Linux server**. Live access requires authorized internal-network access; there is no public demo endpoint. The screenshot and sample above can be viewed without server access. The application's source has not yet been published as a separate GitHub repository.

## Boundaries

Evidence is attached to **outline points**, not every generated sentence. Excerpt matching only checks that text exists in the source; it does not establish that the source supports the claim. Generated body text and manual edits still require review. This version does not implement OCR, retrieval-augmented generation, or automated semantic fact-checking.
