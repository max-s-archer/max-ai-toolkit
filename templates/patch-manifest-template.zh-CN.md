# Patch 清单模板

> 语义源：英文 [Patch Manifest Template](patch-manifest-template.md)。本文档为中文对应版本。

## 使用方式

在私有开发状态仓库中，为每个临时 patch 于 `projects/<project-id>/active/<task-id>/patches/manifest.md` 使用一份清单。清单使 patch 可审计且可安全应用；它不会使 patch 成为产品仓库提交的替代品。

只记录已观察的细节。不要包含机密，也不要用清单掩盖被排除的变更。

---

# Patch 清单：<任务标题>

## 标识

- 项目 ID：`<project-id>`
- 任务 ID：`<task-id>`
- 创建时间：`<UTC timestamp>`
- 源设备或环境：`<device-id or environment>`

## 产品仓库基础

- 远程：`<remote URL or configured remote name>`
- 捕获时分支：`<branch>`
- 基础提交：`<full commit SHA>`
- 应用前的预期目标状态：<所需分支、提交和工作树条件>

## Patch 文件和顺序

1. `<001-base-short-sha.patch>` — SHA-256：`<hash>`

## 覆盖范围

- 包含的变更：<路径和变更类别>
- 明确排除的变更：<未跟踪、已忽略、生成、二进制、本地配置或其他排除项>
- 覆盖范围验证：<如何检查包含项和排除项>

## 应用和验证

- 兼容性检查：<应用前的试运行或等效检查>
- 应用顺序和命令：<确切的已授权方法>
- 应用后的预期 diff：<摘要或比较命令>
- 必要验证：<命令和聚焦手动检查>

## 结果和保留

- 状态：`<pending | applied | failed | retired>`
- 应用结果：<观察到的结果，或 pending>
- 退役或归档条件：<条件和保留决定>
