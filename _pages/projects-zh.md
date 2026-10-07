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

基于 LangChain / LangGraph 的角色工作流、检查点恢复、pgvector 混合检索和带引用 RAG；通过 29 项 Java、17 项 Python 测试与实际浏览器验证。新版已部署内网 HTTPS；使用 DMXAPI-deepseek-v4-flash 完成 6 项同契约单角色/多角色真实任务（15 次调用，4/6 验收通过）及 2/2 项带引用 RAG 验证。失败记录完整保留，结果仅适用于这些开发场景。

[查看项目与验证依据]({{ '/zh/projects/agent-workbench/' | relative_url }}) · [源代码](https://github.com/BStronger1/agent-workbench)

[![Agent Workbench 界面]({{ '/images/agent-workbench.png' | relative_url }})]({{ '/zh/projects/agent-workbench/' | relative_url }})

## [AI PPT生成]({{ '/zh/projects/ai-ppt-generator/' | relative_url }})

将项目材料转化为可编辑幻灯片，并查看大纲要点所依据的原文摘录。应用包含项目答辩流程、证据审查和私有 Linux 服务器部署。

**技术栈：** React / TypeScript、FastAPI、PostgreSQL、Redis / ARQ、LangGraph、python-pptx。

[查看项目与验证结果]({{ '/zh/projects/ai-ppt-generator/' | relative_url }}) · [下载示例 PPTX]({{ '/files/ai-ppt-generator-demo.pptx' | relative_url }})

[![AI PPT生成编辑器，展示来源摘录与缺失证据提示]({{ '/images/ai-ppt-generator-editor.jpg' | relative_url }})]({{ '/zh/projects/ai-ppt-generator/' | relative_url }})
