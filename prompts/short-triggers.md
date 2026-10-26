# Short Triggers

> Semantic source: English. Chinese counterpart:
> [short-triggers.zh-CN.md](short-triggers.zh-CN.md).

## Purpose

Record short author phrases that select an existing Toolkit workflow.
This file is an index only. The linked rule remains authoritative for
checks, authorization, and execution.

## Triggers

- `提交检查`
  - Inspect whether the current changes meet the commit threshold.
  - If not, report the reason and stop.
  - If they do, generate a commit message and stop for review.
  - Authority: [Commit and Push Rule](../rules/git/commit-and-push.md).
- `提交`
  - Create one local commit only after `提交检查` and author review.
  - This does not authorize a push.
  - Authority: [Commit and Push Rule](../rules/git/commit-and-push.md).

Add a new trigger here only when it routes to an existing authoritative
rule, workflow, or skill. Do not define a second procedure in this file.
