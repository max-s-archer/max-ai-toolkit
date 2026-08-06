# 开发交接模板

> 语义源：英文 [Development Handoff Template](development-handoff-template.md)。本文档为中文对应版本。

## 使用方式

在私有开发状态仓库中，为每个活动任务在 `projects/<project-id>/active/<task-id>/handoff.md` 使用一份副本。这是简洁、可同步的工作状态记录；它不替代产品文档、ADR、Git 历史或直接仓库检查。

以已观察的事实替换占位符。不适用的章节可以移除；不要编造缺失信息。

---

# 交接：<任务标题>

## 标识

- 项目 ID：`<project-id>`
- 任务 ID：`<task-id>`
- 状态：`<active | paused | blocked | closed>`
- 最后更新：`<UTC timestamp>`
- 更新设备或环境：`<device-id or environment>`

## 目标和边界

- 目标：<预期结果>
- 范围内：<已授权工作>
- 范围外：<明确非目标>

## 已验证的产品仓库基线

- 远程：`<remote URL or configured remote name>`
- 分支：`<branch>`
- HEAD：`<full commit SHA>`
- 交接时的工作树：`<clean | changed; summarize observed files>`
- 相关产品文档和决策：<链接或路径>

## 已完成工作和证据

- <已完成操作及其支持证据>

## 当前状态和下一步行动

- 当前状态：<当前为真的事项>
- 下一步行动：<最小下一步行动>
- 必要验证：<命令、检查或聚焦手动验证>

## 决策、假设和问题

- 已确认决策：<决策及权威产品记录的链接>
- 假设或推论：<明确标记的事项>
- 未解决问题或阻塞项：<问题、负责人和重要性>

## Patch 传输

- Patch 状态：`<none | pending | applied | retired>`
- 清单：`<relative path or none>`
- 覆盖范围或排除项：<patch 携带及未携带的内容>

## 恢复说明

<接收设备必须验证或不得执行的信息。>
