# Toolkit 使用模型

> 语义源：英文 [Toolkit Consumption Model](consumption-model.md)。本文档为中文对应版本。

## 目的

定义产品仓库如何使用 `max-ai-toolkit`，而无需将其复制到产品仓库，或为每项任务加载整个 Toolkit。

## 模型

`max-ai-toolkit` 是外部、可复用的方法仓库。产品仓库仍拥有其产品事实、实现、项目特定规则和决策。

保持 Toolkit 与产品仓库相互独立。新产品会话开始时，显式提供 Toolkit 定位符，并要求 Agent 在读取任务特定产品上下文前先阅读 Toolkit 启动入口。不要依赖 Agent 隐式发现兄弟仓库。

定位符可以是本地路径、已检出的工作区位置或有意固定的仓库修订。需要可复现性时，在产品仓库的本地 Agent 说明中记录所选定位符或修订。

## 产品仓库启动契约

在启动期间创建或更新产品仓库的 `AGENTS.md`。它必须：

1. 标识 Toolkit 定位符或已批准的引用。
2. 要求新 Agent 会话在项目工作前阅读 `<toolkit>/prompts/project-bootstrap.md`。
3. 标识产品自身的入口文档、架构、决策、验证命令和项目特定覆盖。
4. 说明产品仓库仅在明确且属于项目范围内时覆盖 Toolkit 指引。

项目使用独立的私有开发状态仓库进行跨设备接续时，其 `AGENTS.md` 还应标识该仓库定位符及其中使用的项目 ID。将该仓库只视为临时任务状态和 patch 传输来源；产品代码、产品决策和产品文档仍保留在产品仓库。

将 `author-todo.md`、`author-prompts.md` 和 `agent-proposals.md` 等私有作者工作状态仅保留在开发状态仓库中。不得在产品仓库中创建本地、已忽略、镜像或占位副本。创建或修改这些产物时，阅读[私有工作状态规则](../rules/common/private-working-state.zh-CN.md)。

## 项目特定覆盖协议

Toolkit 提供默认方法。产品仓库仅可通过其 `AGENTS.md` 路由 Agent 阅读的明确本地覆盖，替代适用的 Toolkit 指引。使用 [Toolkit 覆盖模板](../templates/toolkit-override-template.md)，或使用等效的项目本地结构。

每项覆盖必须标识其替代的 Toolkit 指引、项目替代规则、确切范围和所需原因。未被链接的私有提示词、一般偏好或暗示性差异均不是覆盖。

覆盖不得与系统、安全或其他更高优先级要求冲突。当项目材料看似与 Toolkit 不同但不满足明确覆盖要求时，检查相关项目说明和源材料。若冲突或适用性仍不确定，行动前询问作者；不得推断存在覆盖。

在新会话中使用以下形式，并将定位符替换为实际解析的路径或引用：

```text
先阅读 <toolkit-locator>/prompts/project-bootstrap.md，然后阅读本仓库的 AGENTS.md 及其路由到的文档。在提出或编辑任何项目文档或代码前，建立所需上下文。
```

## 渐进式使用

1. 阅读 `prompts/project-bootstrap.md` 和产品的 `AGENTS.md`。
2. 阅读 [Toolkit 架构](architecture.md)和仅适用于任务的政策。
3. 选择该任务需要的角色、工作流、技能和模板。
4. 阅读该任务所需的产品上下文。

除非产品需要明确的本地覆盖，否则不要将 Toolkit 规则复制到产品文档中。链接到 Toolkit 方法，或记录覆盖的范围和原因。

## 版本与更新纪律

- 当任务需要可复现性时，将 Toolkit 修订视为 Agent 工作上下文的一部分。
- 当产品采用较新 Toolkit 修订或相关 Toolkit 政策变更时，重新阅读受影响的 Toolkit 指引。
- 不要将修改 Toolkit 内容作为产品工作的附带副作用。在移除产品特定事实后，通过独立 Toolkit 变更提炼可复用改进。
