# 架构决策记录模板

> 语义源：英文 [Architecture Decision Record Template](adr-template.md)。本文档为中文对应版本。

## 使用方式

仅当已实现的架构决定满足[架构决策记录](../rules/common/architecture-decision-records.zh-CN.md)时，才在目标产品仓库中创建 ADR。实施前提案应记录在已授权任务、迭代、架构评审或技术评估中。Toolkit 提供方法和模板，不持有产品 ADR。

使用下一个四位序号和简洁的小写 kebab-case 标题命名：

```text
docs/decisions/0001-adopt-offline-first-storage.md
```

序列属于目标仓库。追加下一个编号；不得重新编号、复用或改变现有 ADR 标识的用途。将 Inactive ADR 保留为历史决定。重要替代方向应记录在新 ADR 中，且只有替代方案已经实施、接受、commit 并同步后，才使旧 ADR 失效。

---

# ADR-0001: <决定标题>

## 状态

- Value: `Active`
- Updated: YYYY-MM-DD
- Basis: <作者或架构权威接受，以及实现和文档已同步的证据>

## 日期

YYYY-MM-DD

## 背景

描述问题、约束、受影响边界，以及现在需要记录该决定的原因。

## 决定

准确说明已经落地的方向，使其足以指导后续实现和审查。

## 理由

说明该选项为何最适合当前上下文和约束。

## 考虑过的方案

### <方案 A>

- 收益：
- 取舍：

### <方案 B>

- 收益：
- 取舍：

## 后果

描述预期的正面、负面、运维、兼容性、迁移和维护后果。

## 实施说明

适用时记录所需迁移路径、兼容性计划或后续工作。

## 实现与验证证据

- 实现 commit：
- 已同步文档：
- 验证或已接受缺口：
- 此前提案或评估：

## 替代

无

## 失效

- 日期：`Active` 时不适用
- 原因：`Active` 时不适用
- 替代 ADR：无
- 后果：无
