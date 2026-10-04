---
layout: single
title: "Recall Agent"
permalink: /projects/recall-agent/
author_profile: true
---

A personal AI application that combines user-controlled long-term memory, recent conversations and knowledge retrieval. The project explores practical memory management for LLM applications through an inspectable, repeatable workflow.

[Source code](https://github.com/BStronger1/recall-agent) · [Interactive demo](https://bstronger1.github.io/recall-agent/) · [Deployment documentation](https://github.com/BStronger1/recall-agent/blob/main/deploy/turing/README.md)

![Recall Agent demo workspace showing sample memory and context panels]({{ '/images/recall-agent.png' | relative_url }})

*Demo workspace with sample content. The public demo does not call a model or store real account data.*

### What it does

- **User-controlled memory:** add, edit and delete preferences, facts and project context. Long-term memory is saved explicitly by the user.
- **Inspectable context:** combine up to 20 recent messages, six relevant memory entries and five knowledge excerpts; display recalled memory, source references and execution steps with the answer.
- **Self-service accounts:** register and log in without an invitation token, access the same workspace from another device, and bind an existing browser workspace during registration.
- **Personal model APIs:** configure a compatible endpoint, model name and API key; test the connection, save the configuration or delete it. Account workspaces require the user's own model credentials.
- **Knowledge retrieval:** local keyword retrieval supports Chinese and English text. Dify and RAGFlow adapters are implemented for configured site-level workspaces; self-service accounts currently use isolated local knowledge.

### Engineering choices

Java 21 and Spring Boot serve the API and packaged Vue 3 frontend. A single-instance file store persists memory, knowledge and conversation history. Account sessions determine the workspace on the server, rather than trusting a client-supplied workspace identifier.

Personal model keys use AES-GCM encryption at rest and are excluded from API responses and workspace exports. Passwords use salted PBKDF2 hashes; expiring login tokens are stored as hashes. Account requests include access checks and protection against cross-site writes. User-configured model endpoints are restricted to administrator-approved HTTPS hosts.

The full application is deployed in a private Linux user environment with process supervision and persistent storage. Access requires the authorized campus/VPN network; credential entry should use an SSH-encrypted connection or HTTPS. The GitHub Pages link above is a separate demonstration frontend.

### What has been verified

- **19 backend tests:** persistence, memory and retrieval behavior, access control, encrypted model settings, account isolation, login/logout, session expiry and existing-workspace binding.
- **Live model calls:** personal API connection testing, a conversation using the saved personal configuration, and recall of a randomly generated marker from stored memory.
- **Restart and device checks:** account sessions, memory and model configuration survived application restarts; a separate login session accessed the same workspace, and logout revoked that session's access.
- **Frontend checks:** production build and browser inspection of the registration and model-settings interface.

See the [automated tests](https://github.com/BStronger1/recall-agent/tree/main/recall-server/src/test/java/dev/recall), [account smoke test](https://github.com/BStronger1/recall-agent/blob/main/deploy/turing/smoke-accounts.py) and [model-settings smoke test](https://github.com/BStronger1/recall-agent/blob/main/deploy/turing/smoke-model-settings.py).

These checks establish functionality on the tested workflows, not a measured improvement in LLM quality or production-scale reliability. Local retrieval is keyword-based, not vector search. Dify / RAGFlow have fixture-based tests but have not been validated against live services. The current account system does not provide email-based password recovery.

### Project background

I shaped Recall Agent around memory management and a bring-your-own-model workflow, with AI-assisted implementation and deployment. The repository began from an existing project; its [source history and attribution](https://github.com/BStronger1/recall-agent#项目来源) are retained. This iteration adds the memory workspace, retrieval adapters, personal model configuration, account system and deployment tooling.
