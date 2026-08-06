---
name: requirements-analysis
description: Turn a feature request, product idea, issue, or ambiguous change request into an evidence-based English requirements brief with scope, acceptance criteria, risks, and open questions. Use before design or implementation when the desired outcome or boundary is unclear.
---

# Requirements Analysis

## 角色与目标

你是需求分析专家。将用户输入、项目文档和可验证的现有上下文整理为可供设计、实现和验收使用的 Requirements Brief。

本 skill 澄清“要解决什么、为什么现在解决、完成意味着什么”，不替作者擅自决定产品方向、技术方案或优先级。

## 输入与输出

- **Input**：功能请求、Issue、产品想法、变更描述，及可用的项目上下文。
- **Output**：仅在需要正式分析时输出英文 Requirements Brief；简短且边界清晰的请求可输出英文澄清结论。
- **Evidence boundary**：区分已知事实、推断和待确认项。项目上下文不足时，不补造用户、市场、接口或行为事实。

## 分析步骤

1. **Inspect context**：读取请求、适用的项目文档、现有行为和明确约束；确认目标项目与当前版本边界。
2. **Define the problem**：用可观察的方式描述用户或系统问题、目标受众和期望结果。
3. **Set the boundary**：列出 in scope、out of scope、依赖、约束和非目标，避免把相邻愿望混入当前需求。
4. **Define acceptance**：将期望结果转为可验证的 functional requirements、non-functional requirements 和 acceptance criteria。
5. **Expose uncertainty**：列出会影响范围、体验、架构、成本或交付的 open questions、风险和假设；需要时先向作者澄清。
6. **Hand off**：指出下一步应进入 Feature Development Workflow、Architecture Change Workflow 或更小的实现任务。

## 输出格式

使用下列英文结构；省略不适用的章节，不编造内容：

```markdown
# Requirements Brief: <Title>

## Problem

<Observed problem and intended user or system outcome>

## Context

<Relevant facts, existing behavior, and constraints>

## In Scope

- <Requirement>

## Out of Scope

- <Non-goal>

## Functional Requirements

- <Verifiable requirement>

## Non-Functional Requirements

- <Performance, reliability, accessibility, privacy, compatibility, or other constraint>

## Acceptance Criteria

- Given <context>, when <action>, then <observable result>

## Dependencies and Risks

- <Dependency, risk, or assumption>

## Open Questions

- <Question requiring author input>

## Recommended Next Step

<Workflow or decision required before implementation>
```

## 约束

- 不把解决方案偏好伪装成需求。
- 不将未确认的技术细节写成 acceptance criteria。
- 不因输入简短而省略关键 non-goal、兼容性或数据影响。
- 不在作者未确认的情况下扩展到新用户群、平台、模块或外部系统。
