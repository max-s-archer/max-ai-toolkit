# 项目启动提示词

> 语义源：英文 [Project Bootstrap Prompt](project-bootstrap.md)。本文件为中文对应版本。

本提示词用于启动一个新产品项目的 Agent 会话。使用前，将 `<toolkit-locator>` 替换为已确认的 Toolkit 本地路径或版本引用。

在修改项目文档、代码、Git 状态或远端资源之前，先建立以下上下文：

1. 阅读 `<toolkit-locator>/docs/consumption-model.md`。
2. 阅读 `<toolkit-locator>/workflows/new-project.md`。
3. 阅读 `<toolkit-locator>/AGENTS.md`，再只加载其路由到的必要 Policy、Role、Workflow、Skill 和 Template。
4. 阅读目标项目的 `AGENTS.md`。若尚不存在，按 New Project Workflow 处理；但先请作者确认目标仓库和 Toolkit locator。
5. 阅读目标项目已有的 README、架构文档、ADR 和构建/验证说明；只读取当前初始化或任务相关的部分。

## 多语言文档处理

- 以 `.zh-CN.md` 结尾的文档，是对应无语言后缀文档的中文版本。
- 可按理解需要阅读任一语言，或对比阅读两种语言。
- 两个版本的意图一致时，以无语言后缀的英文原版文档为准。
- 若发现中文对应文档与英文源文件存在实质性语义差异，应报告该差异；不得将翻译版本视为项目级覆盖规则。

在任何写操作前，先提供一份简洁的 Context Summary，明确：

- 已读取的 Toolkit 与项目文档
- Toolkit locator 或版本引用
- 当前产品目标、已知范围和未解决事项
- 可用的构建与验证基线，或仍缺失的配置
- 建议使用的 Role、Workflow、Skill 和 Template
- 开始工作前仍需要作者确认的事项

若缺少 Toolkit locator、目标项目路径、产品意图或必要授权，先请求澄清；不要猜测或创建文件。
