---
layout: archive
lang: zh-CN
translation_url: /projects/
title: "项目"
permalink: /zh/projects/
author_profile: true
---

## [Recall Agent — 用户可控记忆的个人 AI 助手]({{ '/zh/projects/recall-agent/' | relative_url }})

管理长期偏好、事实和项目背景，将其与近期对话和检索知识结合，并查看回答所使用的依据。自助账号让记忆和个人模型配置能够跨设备使用。

**技术栈：** Java 21、Spring Boot、Vue 3、Vite、Chat Completions 兼容 API。

通过 19 项后端测试，以及记忆召回、个人 API 配置、跨设备登录和应用重启后持久化的真实模型验证。公开演示使用示例内容；完整服务需要授权校园网 / VPN 访问。

[项目详情与验证]({{ '/zh/projects/recall-agent/' | relative_url }}) · [交互演示](https://bstronger1.github.io/recall-agent/) · [源代码](https://github.com/BStronger1/recall-agent)

[![Recall Agent 演示工作区，展示示例记忆与上下文面板]({{ '/images/recall-agent.png' | relative_url }})]({{ '/zh/projects/recall-agent/' | relative_url }})

## [Agent Workbench — 项目记忆与浏览器验证修复]({{ '/zh/projects/agent-workbench/' | relative_url }})

实现“需求与记忆上下文 → 模型生成 HTML → 浏览器验收 → 错误反馈修复”的 AI 应用工作流，支持三种上下文策略、Token 预算、运行证据和加密保存的用户模型配置。

**技术栈：** Java 21、Spring Boot、Vue 3、TypeScript、Playwright。

通过 25 项后端测试、浏览器端到端检查和 36 个确定性演示案例。真实模型集成已实现，但尚未通过实际 API 调用验收；演示结果验证的是流程，不是模型性能。

[查看项目与验证依据]({{ '/zh/projects/agent-workbench/' | relative_url }}) · [源代码](https://github.com/BStronger1/agent-workbench)

[![Agent Workbench 界面]({{ '/images/agent-workbench.png' | relative_url }})]({{ '/zh/projects/agent-workbench/' | relative_url }})

## [AI PPT生成]({{ '/zh/projects/ai-ppt-generator/' | relative_url }})

将项目材料转化为可编辑幻灯片，并查看大纲要点所依据的原文摘录。应用包含项目答辩流程、证据审查和私有 Linux 服务器部署。

**技术栈：** React / TypeScript、FastAPI、PostgreSQL、Redis / ARQ、LangGraph、python-pptx。

[查看项目与验证结果]({{ '/zh/projects/ai-ppt-generator/' | relative_url }}) · [下载示例 PPTX]({{ '/files/ai-ppt-generator-demo.pptx' | relative_url }})

[![AI PPT生成编辑器，展示来源摘录与缺失证据提示]({{ '/images/ai-ppt-generator-editor.jpg' | relative_url }})]({{ '/zh/projects/ai-ppt-generator/' | relative_url }})
