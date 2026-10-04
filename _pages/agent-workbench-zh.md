---
layout: single
lang: zh-CN
translation_url: /projects/agent-workbench/
title: "Agent Workbench"
permalink: /zh/projects/agent-workbench/
author_profile: true
---

一个将需求转化为可验证产物的个人 AI 工作台，具备显式项目记忆和基于来源的报告能力。

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

Java 21 和 Spring Boot 提供 API 并托管打包后的 Vue / TypeScript 前端。项目快照在无外部数据库的情况下持久化状态。生成产物保持为自包含 HTML，服务不会安装或执行模型生成的 npm 项目。浏览器预览使用隔离 iframe 和内容安全策略，验证进程阻止外部请求。

私有部署通过专用本地 CA 支持 HTTPS。已测试证书链与 IP 身份验证、浏览器工作流程，以及已有工作区 Cookie 向 Secure Cookie 的迁移。客户端设备需要显式信任本地 CA 后才能正常访问。

### 已验证内容

25 项后端测试覆盖持久化、归属隔离、记忆更新、失败处理、修复次数限制、预算检查、加密模型配置和请求路由。浏览器检查覆盖生成流程、检索、报告和模型设置。在 36 个确定性演示案例中，18 个首次通过，另外 18 个故意注入按钮故障的案例在预设修复后通过。这验证的是这些测试案例中的工作流程，**不代表**真实模型质量或记忆检索的有效性。

真实模型 HTTP 适配器已实现；服务商实际兼容性、生成质量与模型对比，仍需配置 API 后验证。

### 个人项目

我开发 Agent Workbench，希望将应用构建、项目知识和开发报告整合到同一工作区。实现内容包括记忆版本管理、验收约定、有限次数修复、浏览器验证、用户自定义模型、证据报告和部署工具。
