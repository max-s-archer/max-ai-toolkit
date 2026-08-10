# max-ai-toolkit

[English](README.md)

> 语义源：英文 [README](README.md)。本文件为中文对应版本。

面向 Max GitHub 项目的个人 AI Agent 工程方法库。

`max-ai-toolkit` 是一个公开的个人方法仓库，提供可复用的 AI Agent 开发基础设施，而不保存具体产品的需求或实现。它优先适配 Max 的项目生态，而非追求通用产品化。

## 从这里开始

1. 阅读 [Toolkit Architecture](docs/architecture.md)，了解适用边界、目录职责、文档优先级与渐进加载模型。
2. 阅读 [AGENTS.md](AGENTS.md)，了解 Agent 的最小路由和变更协议。
3. 只加载当前任务所需的 Policy、Rule、Role、Workflow、Skill、Template 和项目上下文。
4. 修改具体项目之前，先读取其自身文档和明确规则。

## 仓库导航

| 区域 | 用途 |
| --- | --- |
| [`policies/`](policies/) | 跨项目治理与约束 |
| [`principles/`](principles/) | 长期工程价值观与决策理由 |
| [`rules/`](rules/) | 可执行的 Agent 行为约束 |
| [`skills/`](skills/) | 面向具体任务的可复用方法 |
| [`roles/`](roles/) | Agent 职责定义 |
| [`workflows/`](workflows/) | 可复用的项目初始化、发布、功能开发、Bug 修复与架构变更流程 |
| [`templates/`](templates/) | 可复用的项目概览、ADR、Release Notes、作者确认与私有工作状态输出骨架 |
| [`docs/`](docs/) | Toolkit 的[架构](docs/architecture.md)、[消费模型](docs/consumption-model.md)与[迁移指南](docs/migration-guide.md) |
| [`prompts/`](prompts/) | 组合已验证 Toolkit 资产的轻量任务入口 |

## 语言

英文是对外默认语言；当有助于 Max 的内部维护时可使用中文；只有长期有价值的内容才维护双语版本。详见 [Language Policy](policies/language-policy.md)。

## 读取顺序

采用渐进加载：先读取 Toolkit 架构和适用 Policy，再读取当前 Role 或 Workflow，然后按需读取 Skill 或 Template，最后读取相关项目上下文。完整优先级见 [Toolkit Architecture](docs/architecture.md#document-precedence)。
