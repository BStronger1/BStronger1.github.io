---
layout: single
lang: zh-CN
translation_url: /projects/agent-workbench/
title: "Agent Workbench"
permalink: /zh/projects/agent-workbench/
author_profile: true
---

一个集应用生成、项目知识检索和自动验收于一体的个人 AI 工作台。新增可选 Python AI 服务，连接 LangChain、LangGraph、向量检索与规划/编码/评审角色协作。

[GitHub](https://github.com/BStronger1/agent-workbench) · [升级架构与运行方法](https://github.com/BStronger1/agent-workbench/blob/main/docs/AI-UPGRADE.md)

### AI 技术与工程实现

- **Agent 工作流：** LangGraph 管理规划、人工确认、编码、浏览器检查、评审与有界修复；LangChain 连接兼容模型接口，Pydantic 校验结构化输出。
- **状态恢复：** SQLite 检查点支持单实例恢复，调用账本保存完成结果并阻止不确定请求自动重放；不承诺供应商端 exactly-once。
- **RAG 与项目记忆：** 本地多语言 MiniLM 提供 384 维向量，pgvector 余弦检索与中文关键词检索通过 RRF 融合。按空间和项目过滤，删除失效版本，回答检查引用 ID 是否来自召回集合。
- **可执行验收：** Playwright 执行勾选、输入、点击和精确文本/变化断言；验收契约固定后，编码和修复不能修改标准。浏览器证据决定最终结果。
- **模型与数据边界：** 用户自填接口、模型和 Key；AES-256-GCM 加密配置，凭据不进入状态图。有限队列、预算预检查和角色调用记录约束执行。

Python / FastAPI · LangChain · LangGraph · PostgreSQL / pgvector · Embedding / RAG · Playwright · Java / Spring Boot · Vue / TypeScript

Spring Boot 保留用户空间隔离、API 和队列，Vue 提供工作台界面；FastAPI 仅绑定本机并使用内部认证。业务快照与检查点仍按单实例设计，未实现多实例分布式调度。

### 验证结果与范围

工程验证覆盖 Java 后端、Python 状态图、暂停恢复、调用去重、真实 PostgreSQL/pgvector、实际 ONNX Embedding 以及 Chromium 交互。六条中文检索开发样例中，混合 Recall@3 为 5/6，关键词为 2/6；未使用独立保留集，不能外推效果。[检索原始记录](https://github.com/BStronger1/agent-workbench/blob/main/evidence/retrieval-fixtures.json)

基础 Java 链路曾完成 36 个确定性演示验收，以及 DMXAPI-deepseek-v4-flash 的 6 项真实任务、8 次调用，首轮和最终均通过 4/6。两项清单任务的修复仍未满足原单击验收，失败证据完整保留。[真实测试报告](https://github.com/BStronger1/agent-workbench/blob/main/docs/LIVE-RESULTS.md)

新版已部署内网 HTTPS；使用 DMXAPI-deepseek-v4-flash 完成 6 项同契约单角色/多角色真实任务（15 次调用，4/6 验收通过）及 2/2 项带引用 RAG 验证。失败记录完整保留，结果仅适用于这些开发场景。 [配对任务、RAG 与调试记录](https://github.com/BStronger1/agent-workbench/blob/main/docs/GRAPH-LIVE-RESULTS.md)

![基础链路真实模型生成的研究任务看板]({{ '/images/agent-workbench-live.png' | relative_url }})

### 部署与微调状态

图编排版已部署 Linux 内网 HTTPS，使用专用本地 CA；FastAPI 和私有 PostgreSQL 仅监听本机。通过 17 项部署端 Python 测试、5 项 Node 契约/控制测试和实际网页回归，Java 回归为 29 项。服务未配置整机重启后的自动启动。

已实现待审校训练样本导出和按任务分组，尚未进行 LoRA/QLoRA 训练，不宣称微调效果。
