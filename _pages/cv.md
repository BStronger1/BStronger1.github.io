---
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
### [AI PPT生成 — AI Presentation Generator]({{ '/projects/ai-ppt-generator/' | relative_url }})
**AI-assisted adaptation · October 2026**

React / TypeScript · FastAPI · PostgreSQL · Redis / ARQ · LangGraph · python-pptx

* Extended an existing presentation generator with a project-defense brief covering audience, duration, focus, and the distinction between completed work and future plans.
* Added outline-level source excerpts, reference validation, and invalidation of citations after edits; exposed evidence for review in the editor and preserved it in PPTX speaker notes.
* Deployed the application, worker, database, and queue in an isolated Linux user environment with persistent storage and process supervision; verified a six-slide real-model generation/export workflow and data retention after service restarts.

Based on [yuyuanweb/ai-ppt-generator](https://github.com/yuyuanweb/ai-ppt-generator). Live access is restricted to the authorized internal network; a [project walkthrough and sample PPTX]({{ '/projects/ai-ppt-generator/' | relative_url }}) are publicly available.

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
