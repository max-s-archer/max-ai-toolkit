# 跨设备恢复提示词

> 语义源：英文 [Cross-Device Resume Prompt](cross-device-resume.md)。本文档为中文对应版本。

在另一台设备上恢复经有意交接的任务时使用此提示词。请以已确认的值替换所有占位符。

```text
跨设备恢复项目 <project-id> 的任务 <task-id>。

在提出建议或编辑任何内容之前：
1. 阅读 <toolkit-locator>/workflows/cross-device-continuation.md 和目标产品仓库的 AGENTS.md。
2. 同步并阅读 <development-state-repository-locator>/projects/<project-id>/project.md。
3. 阅读 <development-state-repository-locator>/projects/<project-id>/active/<task-id>/handoff.md，以及存在时的 patch 清单。
4. 识别目标设备的操作系统和 shell。同步产品仓库，然后检查其远程、分支、完整 HEAD 提交、工作树状态、相关 diff，以及交接记录中指出的文件。
5. 将观察到的仓库状态与交接记录和 patch 清单比较。将交接记录视为待验证的声明，而不是事实来源。

报告一份恢复摘要，其中包括已确认的项目和任务标识符；目标设备的操作系统和 shell；观察到的分支、HEAD 和工作树状态；已确认的已完成工作、下一步行动和验证；以及所有差异、缺失产物、冲突或未解决问题。

在验证 patch 的基础提交与覆盖范围，并且兼容性检查成功前，不得应用 patch。没有匹配的目标环境或已明确验证的替代方案时，不得执行平台或 shell 特定命令。若证据冲突，在扩大范围、强制应用 patch、覆盖变更或猜测缺失上下文前停止并询问作者。
```
