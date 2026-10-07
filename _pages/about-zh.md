---
lang: zh-CN
translation_url: /
permalink: /zh/
title: "Yangbin Zou"
author_profile: true
---

我目前是[北京师范大学](https://www.bnu.edu.cn/)[认知神经科学与学习国家重点实验室](https://brain.bnu.edu.cn/)的硕士研究生。

我的研究兴趣位于认知神经科学与机器学习的交叉领域，尤其关注记忆。我希望探索人类记忆的原理如何启发大语言模型的记忆系统设计，以及模型研究如何反过来帮助理解人类记忆。

研究兴趣
======
* 学习与记忆的认知神经科学
* 记忆增强的大语言模型
* 信息检索与知识组织

精选项目
======
**[Recall Agent — 用户可控记忆的个人 AI 助手]({{ '/zh/projects/recall-agent/' | relative_url }})** 将可编辑的长期记忆、近期会话和带来源引用的知识检索结合起来。用户可自助注册、配置自己的模型 API，并跨设备访问同一工作区。私有部署已通过真实模型记忆召回与重启持久化验证。[交互演示](https://bstronger1.github.io/recall-agent/) · [源代码](https://github.com/BStronger1/recall-agent)

**[AI PPT生成]({{ '/zh/projects/ai-ppt-generator/' | relative_url }})** 将项目材料转化为可编辑幻灯片，并为大纲要点提供原文摘录。应用包含项目答辩流程、证据审查和私有 Linux 服务器上的持久化部署。项目页面提供截图与可下载示例。

**[Agent Workbench](https://github.com/BStronger1/agent-workbench)** 是一个个人 AI 工作台，连接项目记忆、自包含应用生成、浏览器交互检查和有限次数修复。它支持带来源的文档检索、开发报告，以及 API 密钥加密存储的用户自定义模型。技术栈包括 Python / FastAPI、LangChain、LangGraph、pgvector、Java / Spring Boot、Vue / TypeScript 和 Playwright。[项目详情]({{ '/zh/projects/agent-workbench/' | relative_url }})

基于 LangChain / LangGraph 的角色工作流、检查点恢复、pgvector 混合检索和带引用 RAG；通过 29 项 Java、20 项 Python 测试与实际浏览器验证。新版已部署内网 HTTPS；使用 DMXAPI-deepseek-v4-flash 完成 6 项同契约单角色/多角色真实任务（15 次调用，4/6 验收通过）及 2/2 项带引用 RAG 验证。失败记录完整保留，结果仅适用于这些开发场景。

原失败的清单场景已修复，使用同一模型与验收契约，在单角色和多角色下定向复测均通过（2/2）；保留此前完整评测及本轮中间失败。此次修复完成本地完整链路验证，服务器同步待 SSH 恢复。 [修复报告](https://github.com/BStronger1/agent-workbench/blob/main/docs/CHECKLIST-REGRESSION.md)

动态
======
* **2026 年 10 月：** 将 Recall Agent 加入项目集，支持账号绑定记忆、个人模型密钥加密保存，并完成私有 Linux 服务器上的真实模型部署验证。
* **2026 年 10 月：** 将 AI PPT生成加入项目集，完成材料上传、真实模型生成、可编辑 PPTX 导出以及服务重启后的持久化验证。

联系
======
欢迎通过电子邮件联系我（见侧栏），交流研究或潜在合作。
