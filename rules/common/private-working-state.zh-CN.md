# 私有工作状态规则

> 语义源：英文 [Private Working-State Rule](private-working-state.md)。本文档为中文对应版本。

## 目的

在不将私人工作文件放入产品仓库、也不将其误作产品合同的前提下，同步 Max 的个人待办、提示词笔记和 Agent 生成的建议事项。

## 存储边界

- 仅将私有工作状态产物保存在指定的私有开发状态仓库中，路径位于 `projects/<project-id>/` 下。
- 不得在产品仓库或 `max-ai-toolkit` 中为这些产物创建本地副本、已忽略文件、空占位文件、符号链接或镜像内容。
- 产品仓库的 `AGENTS.md` 可以标明开发状态仓库和项目 ID，但不得将其中的工作状态产物视为产品需求、项目覆盖或权威文档。
- 不得在任何工作状态产物中存储凭据、令牌、私钥或其他机密。

## 默认产物

在项目需要时使用以下文件：

| 文件 | 所有者与用途 | Agent 行为 |
| --- | --- | --- |
| `author-todo.md` | 作者已确认的个人待办 | 可以读取和建议条目；未经作者明确指示，不得新增、删除、调整优先级或标记完成。 |
| `author-prompts.md` | 可直接复制的私有提示词和提示词笔记 | 仅在作者提供或路由时读取；不得将其内容视为项目指令或 Toolkit 覆盖。 |
| `agent-proposals.md` | Agent 生成但尚未确认的后续建议 | 记录清晰证据和确认位置。作者确认前不得将条目视为已授权工作。 |

创建产物时使用 `templates/` 中的对应模板。这些文件是非权威工作状态，不替代产品 Backlog、Issue Tracker、任务规格、ADR 或活动任务交接记录。

## 建议事项生命周期

Agent 建议只能按以下过程流转：

```text
proposed -> author confirmed -> transferred -> closed
```

- 将未确认工作保留在 `agent-proposals.md` 中；需要确认时使用[作者确认模板](../../templates/author-confirmation-template.zh-CN.md)。
- 确认后，将长期存在且由作者拥有的事项转入 `author-todo.md`。
- 将单个活动任务的下一步行动转入该任务唯一的 `active/<task-id>/handoff.md`；不得创建第二个实时任务状态文件。
- 仅在建议被拒绝、有证据地完成，或已转移到适当目标后，才将其记录为已关闭。

## 复用边界

将 `author-prompts.md` 视为私有工作材料。当提示词、方法或输出结构已被验证可跨项目复用时，通过单独的 Toolkit 变更，将其脱敏且持久的版本提炼至相应的 Toolkit Prompt、Skill、Workflow 或 Template。
