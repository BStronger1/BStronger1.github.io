---
layout: single
lang: zh-CN
translation_url: /projects/recall-agent/
title: "Recall Agent"
permalink: /zh/projects/recall-agent/
author_profile: true
---

一个结合用户可控长期记忆、近期会话和知识检索的个人 AI 应用。项目通过可检查、可重复的工作流程，探索大语言模型应用中的实际记忆管理。

[源代码](https://github.com/BStronger1/recall-agent) · [交互演示](https://bstronger1.github.io/recall-agent/) · [部署文档](https://github.com/BStronger1/recall-agent/blob/main/deploy/turing/README.md)

![Recall Agent 演示工作区，展示示例记忆与上下文面板]({{ '/images/recall-agent.png' | relative_url }})

*图中为使用示例内容的演示工作区。公开演示不调用模型，也不保存真实账号数据。*

### 核心功能

- **用户可控记忆：** 添加、编辑和删除偏好、事实与项目背景。长期记忆由用户显式保存。
- **可检查的上下文：** 结合最多 20 条近期消息、六条相关记忆和五个知识片段；回答同时展示召回记忆、来源引用和执行步骤。
- **自助账号：** 无需邀请码即可注册登录，支持跨设备访问同一工作区，并在注册时绑定已有浏览器工作区。
- **个人模型 API：** 配置兼容接口、模型名和 API 密钥，支持测试连接、保存与删除。账号工作区须使用用户自己的模型凭据。
- **知识检索：** 本地关键词检索支持中文和英文。已为配置好的站点工作区实现 Dify 和 RAGFlow 适配器；自助账号目前使用独立的本地知识库。

### 工程设计

Java 21 和 Spring Boot 提供 API 并托管打包后的 Vue 3 前端。单实例文件存储持久化保存记忆、知识与会话历史。工作区归属由服务端账号会话确定，不依赖客户端提交的工作区标识。

个人模型密钥采用 AES-GCM 加密保存，不在 API 响应中返回，也不进入工作区导出文件。密码使用加盐 PBKDF2 哈希，带有效期的登录令牌也只保存哈希。账号请求经过访问校验，并对跨站写入进行防护。用户配置的模型接口仅允许管理员批准的 HTTPS 域名。

完整应用部署在私有 Linux 用户环境中，配置进程守护和持久化存储。访问需要授权校园网 / VPN；填写凭据时应使用 SSH 加密连接或 HTTPS。上方 GitHub Pages 链接是独立的演示前端。

### 已验证内容

- **19 项后端测试：** 持久化、记忆与检索行为、访问控制、加密模型配置、账号隔离、登录 / 退出、会话过期和已有工作区绑定。
- **真实模型调用：** 个人 API 连接测试、使用已保存个人配置完成对话，以及从已保存记忆中召回随机生成的测试标记。
- **重启与跨设备检查：** 应用重启后，账号会话、记忆与模型配置仍然保留；另一登录会话可访问同一工作区，退出后该会话的访问权限失效。
- **前端检查：** 生产构建，以及注册和模型设置界面的浏览器检查。

参见[自动测试](https://github.com/BStronger1/recall-agent/tree/main/recall-server/src/test/java/dev/recall)、[账号冒烟测试](https://github.com/BStronger1/recall-agent/blob/main/deploy/turing/smoke-accounts.py)和[模型设置冒烟测试](https://github.com/BStronger1/recall-agent/blob/main/deploy/turing/smoke-model-settings.py)。

这些检查证明了已测试流程的功能行为，不代表已测得 LLM 质量提升或生产规模可靠性。本地检索使用关键词，不是向量搜索。Dify / RAGFlow 已通过固定响应测试，但尚未对接真实服务验收。当前账号系统不提供邮件找回密码。

### 项目背景

我围绕记忆管理和用户自带模型的使用方式设计 Recall Agent，并借助 AI 辅助完成实现与部署。仓库以已有项目为起点，保留了[来源历史与署名说明](https://github.com/BStronger1/recall-agent#项目来源)。本次迭代增加了记忆工作区、检索适配器、个人模型配置、账号系统和部署工具。
