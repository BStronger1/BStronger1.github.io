---
layout: single
lang: zh-CN
translation_url: /projects/agent-workbench/
title: "Agent Workbench"
permalink: /zh/projects/agent-workbench/
author_profile: true
---

一个围绕大模型应用生成构建的个人 AI 工作台：将项目记忆注入模型上下文，以浏览器验收结果驱动有限次数代码修复，并记录版本、耗时与 Token 用量。

[GitHub 仓库](https://github.com/BStronger1/agent-workbench) · [架构](https://github.com/BStronger1/agent-workbench/blob/main/docs/ARCHITECTURE.md) · [验证记录](https://github.com/BStronger1/agent-workbench/blob/main/docs/EVALUATION.md)

![Agent Workbench 界面]({{ '/images/agent-workbench.png' | relative_url }})

### 核心功能

- **应用工作室：** 生成自包含 HTML，明确验收要求，执行浏览器交互检查和有限次数修复，保存尝试记录并支持版本选择。
- **项目记忆：** 对约束、决策与经验进行版本管理；被替代的条目不再生效，检索上下文保留来源 ID。
- **项目知识：** 导入文本 / Markdown，使用关键词检索并提供段落级引用。
- **报告：** 根据记录的来源与运行依据生成 Markdown 开发报告。
- **评估：** 区分演示与真实运行，记录延迟及使用量，并提供可复现的验收测试数据。
- **模型设置：** 用户提供自己的接口、模型名和 API 密钥；配置按浏览器工作区加密保存，支持连接测试、启用 / 禁用和删除。

### 工程设计

核心 AI 链路为：需求与记忆检索 → Chat Completions 请求 → HTML 结构校验 → Playwright 文本与交互验收 → 将失败原因和上一版代码反馈给模型。修复最多 3 次，调用前检查 Token 预算；任务使用 2 个执行线程与 12 个排队槽，避免无限排队。知识检索与报告整理目前采用确定性逻辑，不将它们计为模型生成能力。

Java 21 和 Spring Boot 提供 API 并托管打包后的 Vue / TypeScript 前端。项目快照在无外部数据库的情况下持久化状态。生成产物保持为自包含 HTML，服务不会安装或执行模型生成的 npm 项目。浏览器预览使用隔离 iframe 和内容安全策略，验证进程阻止外部请求。

私有部署通过专用本地 CA 支持 HTTPS。已测试证书链与 IP 身份验证、浏览器工作流程，以及已有工作区 Cookie 向 Secure Cookie 的迁移。客户端设备需要显式信任本地 CA 后才能正常访问。

### 已验证内容

25 项后端测试覆盖持久化、归属隔离、记忆更新、失败处理、修复次数限制、预算检查、加密模型配置和请求路由。浏览器检查覆盖生成流程、检索、报告和模型设置。在 36 个确定性演示案例中，18 个首次通过，另外 18 个故意注入按钮故障的案例在预设修复后通过。这验证的是这些测试案例中的工作流程，**不代表**真实模型质量或记忆检索的有效性。

2026-10-07 使用 `DMXAPI-deepseek-v4-flash` 完成 6 个真实任务、8 次生成/修复调用，首轮和最终均通过 4/6。两项清单任务因勾选前置条件不符合单击验收，修复后仍失败，已保留记录与归因。该开发场景结果不能外推为通用成功率或记忆收益。

供应商返回输入 4,324、输出 12,099 Token，平均每任务耗时 60.21 秒。事后隔离复查显示先勾选再点击可更新数量，但未修改原验收结论。

[真实测试完整报告与原始记录](https://github.com/BStronger1/agent-workbench/blob/main/docs/LIVE-RESULTS.md)

![真实模型生成的研究任务看板]({{ "/images/agent-workbench-live.png" | relative_url }})

### 个人项目

我开发 Agent Workbench，希望将应用构建、项目知识和开发报告整合到同一工作区。实现内容包括记忆版本管理、验收约定、有限次数修复、浏览器验证、用户自定义模型、证据报告和部署工具。
