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

### Agent Workbench — 项目记忆驱动的 AI 应用生成与自动验收工作台
**个人项目 · 2026 年 10 月**

[源代码](https://github.com/BStronger1/agent-workbench) · [项目概览]({{ '/zh/projects/agent-workbench/' | relative_url }})

Java 21 · Spring Boot · Vue 3 / TypeScript · Playwright · Chat Completions 兼容接口

* 实现大模型应用生成工作流：将用户需求、项目记忆和验收要求组装为模型上下文，解析 HTML 产物，通过 Playwright 检查页面文本与按钮交互，将失败原因和上一版代码回传模型，支持最多 3 次修复与版本回退。
* 实现项目约束、决策和经验的版本化管理，采用中文双字与关键词匹配检索上下文，支持无记忆、近期需求、检索记忆三种策略，保留召回来源与失效版本。
* 实现用户自选模型与 API Key 配置，采用 AES-256-GCM 加密和浏览器空间隔离；为生成任务加入有限队列、Token 预算检查，以及耗时、尝试次数和供应商用量记录。
* 完成 25 项后端测试、浏览器端到端验证和 36 项确定性演示验收，部署 Linux 内网 HTTPS 服务。使用 `DMXAPI-deepseek-v4-flash` 完成 6 项真实任务评测（8 次生成/修复调用、4 项验收通过），定位清单勾选前置条件与单击验收的不一致，保留两项失败修复证据。

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
