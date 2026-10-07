---
layout: archive
lang: zh-CN
translation_url: /cv/
title: "简历"
permalink: /zh/cv/
author_profile: true
---

教育背景
======
* 北京师范大学，认知神经科学与学习国家重点实验室，认知神经科学硕士（在读）
* 理学学士，20XX

研究兴趣
======
* 学习与记忆的认知神经科学
* 记忆增强的大语言模型
* 信息检索与知识组织

项目经历
======
### [Recall Agent — 用户可控记忆的个人 AI 助手]({{ '/zh/projects/recall-agent/' | relative_url }})
**个人项目 · 2026 年 10 月 · AI 辅助开发**

Java 21 · Spring Boot · Vue 3 · Chat Completions 兼容 API

* 构建记忆辅助对话流程，结合近期消息、用户显式保存的偏好 / 事实 / 项目背景与检索知识，并在回答旁展示召回记忆及来源引用。
* 增加自助注册、持久登录和账号绑定工作区，支持跨设备访问与已有浏览器工作区绑定。新账号使用用户自己的模型 API，密钥采用 AES-GCM 加密存储。
* 实现本地关键词检索及 Dify / RAGFlow 适配器；账号工作区目前使用独立的本地知识库。外部适配器已通过固定响应测试，仍需对接真实服务单独验证。
* 将前后端一体化部署到私有 Linux 服务器，配置持久化存储和进程守护；通过 19 项后端测试，以及记忆召回、账号登录、凭据隔离和重启持久化的真实模型验证。

[源代码](https://github.com/BStronger1/recall-agent) · [交互演示](https://bstronger1.github.io/recall-agent/) · [实现与验证]({{ '/zh/projects/recall-agent/' | relative_url }})

### [AI PPT生成]({{ '/zh/projects/ai-ppt-generator/' | relative_url }})
**AI 产品 · 2026 年 10 月**

React / TypeScript · FastAPI · PostgreSQL · Redis / ARQ · LangGraph · python-pptx

* 增加账号级模型选择、API 密钥加密、模型发现和连接测试，实现用户间的凭据隔离。
* 实现六类受众预设与 AI 叙事规划，参考认知负荷、多媒体学习和精加工原则，将规划应用到页面角色、视觉结构、时长分配和演讲备注中。
* 增加大纲级原文摘录、引用校验和编辑后的引用失效处理，在编辑器中展示证据供审查，并将其保留在 PPTX 演讲备注中。
* 在隔离的 Linux 用户环境中部署应用、工作进程、数据库和队列，配置持久化存储与进程守护；验证六页幻灯片的真实模型生成 / 导出流程，以及服务重启后的数据保留。

完整服务仅限授权内网访问；公开页面提供[项目介绍与示例 PPTX]({{ '/zh/projects/ai-ppt-generator/' | relative_url }})。

### Agent Workbench — 基于 LangGraph 与 RAG 的 AI 应用开发工作台
**个人项目 · 2026 年 10 月**

[源代码](https://github.com/BStronger1/agent-workbench) · [项目概览]({{ '/zh/projects/agent-workbench/' | relative_url }})

Python / FastAPI · LangChain · LangGraph · PostgreSQL / pgvector · Embedding / RAG · Playwright · Java / Spring Boot · Vue / TypeScript

* 基于 LangChain 与 LangGraph 构建需求规划、代码生成、浏览器验收、独立评审及有界修复工作流；支持单角色与多角色模式、计划人工确认和持久化检查点恢复，通过调用账本复用已完成结果，阻止不确定请求自动重放。
* 实现 RAG 知识模块：使用本地多语言 Embedding 与 pgvector 存储项目文档和有效记忆，融合中文双字/关键词检索与向量召回，通过 RRF 排序、空间/项目过滤和来源 ID 校验提供带引用回答。
* 将 Playwright 验收升级为勾选、输入、点击及结果断言的结构化契约，在生成前固定验收标准，将执行错误与评审意见回传编码角色，保存失败产物、截图和修复记录。
* 支持用户自选模型及 AES-256-GCM 加密密钥配置，使用有限任务队列、调用前 Token 预算检查及分角色调用用量记录；保留 Java 基础流程与演示兼容性。
* 完成 29 项 Java、20 项 Python 回归及真实 pgvector/Embedding、浏览器集成验证；使用 DMXAPI-deepseek-v4-flash 完成 6 项同契约单/多角色任务（15 次调用，4/6 通过）及 2/2 项带引用 RAG 验证，保留失败证据。

已部署内网 HTTPS。结果来自自编开发场景，未证明多角色质量提升；未进行模型微调。[验证报告](https://github.com/BStronger1/agent-workbench/blob/main/docs/GRAPH-LIVE-RESULTS.md)

原失败的清单场景已修复，使用同一模型与验收契约，在单角色和多角色下定向复测均通过（2/2）；保留此前完整评测及本轮中间失败。此次修复完成本地完整链路验证，服务器同步待 SSH 恢复。 [修复报告](https://github.com/BStronger1/agent-workbench/blob/main/docs/CHECKLIST-REGRESSION.md)

技能
======
* 编程：Python
* 机器学习 / 深度学习
* 数据分析

论文
======
<ul>{% for post in site.publications reversed %}
  {% include archive-single-cv.html %}
{% endfor %}</ul>

学术服务与社会活动
======
* （请补充学术服务、审稿或志愿活动。）
