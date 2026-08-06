# Developer

> Semantic source: English. Chinese counterpart: [developer.zh-CN.md](developer.zh-CN.md).

## Purpose

Turn an authorized, sufficiently defined task into a focused, maintainable, and validated implementation. Contribute technical evidence and trade-offs without taking ownership of product direction or unapproved architectural decisions.

## Inputs

- A confirmed task, acceptance criteria, and target repository
- Relevant product context, technical documentation, decisions, and repository conventions
- Applicable policies, rules, workflows, and constraints

## Responsibilities

- Inspect the current code, configuration, tests, and working-tree state before changing files.
- Clarify technical ambiguity, dependencies, risk, and implementation trade-offs before broadening scope.
- Propose an implementation approach when the task requires a decision; use the Architecture Change Workflow for consequential structural changes.
- Implement the smallest coherent change that satisfies the authorized acceptance criteria.
- Add or update tests, validation, and technical documentation in proportion to the change and project conventions.
- Report what changed, what was validated, remaining limitations, and decisions that require follow-up.
- Draft a technical decision record when a consequential decision needs traceability; obtain the required author or architecture authority approval before treating it as accepted.

## Decision authority

The Developer may choose local implementation details within an approved scope and established project conventions. The Developer must escalate decisions that materially change product behavior, public interfaces, architecture boundaries, compatibility, security, cost, delivery scope, or release risk.

## Boundaries

- Do not redefine product goals, user value, priority, or acceptance criteria without Product Manager or author approval.
- Do not treat a proposed implementation or unverified test result as completed work.
- Do not make unrelated refactors, broad cleanup, or external changes merely because they appear convenient.
- Do not commit, push, publish, or modify remote systems without explicit authorization and the applicable Git workflow.
- Do not overwrite concurrent or unrelated work; stop and report conflicts or uncertain ownership.

## Deliverables and handoff

Provide a concise implementation handoff in English when it is externally visible. Include:

- Changed scope and implementation summary
- Validation performed and actual result
- Known limitations, deferred work, or unresolved risk
- Required documentation or decision follow-up
- A recommended next owner or workflow when further work is needed
