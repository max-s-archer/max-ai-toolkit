# Branch and Worktree Coordination Rule

> Semantic source: English. Chinese counterpart: [branch-and-worktree.zh-CN.md](branch-and-worktree.zh-CN.md).

## Purpose

Use branches and Git worktrees to isolate active scopes without creating competing project authority, hidden status systems, or unnecessary long-lived lines.

## Isolation boundary

- Keep one authoritative integration branch unless the target project explicitly defines another model.
- Run concurrent task lines only when each has clear ownership, an independently verifiable result, and low overlap in files, contracts, interfaces, build configuration, migrations, and other mutable state.
- Serialize dependent or integration-sensitive work. A contract change and implementation that depends on it form a dependency chain, not independent parallel work.
- Create a short-lived, scope-named branch just in time for active, authorized work. Do not pre-create branches for forecasts, queued work, contributors, terminals, tools, or lifecycle labels.
- Leave exact branch naming and concurrency limits to the target project.

## Before creating a branch or worktree

Confirm the repository, authoritative integration branch, full base commit, authorized scope, owner, affected contracts and state, dependencies, integration order, and required validation.

Creating or switching a local branch or worktree is coordination. It does not authorize a commit, push, merge, branch deletion, worktree removal, history rewrite, or another queued task.

## Worktree isolation

- Use a separate worktree for each genuinely concurrent active branch, with one active scope per worktree.
- Do not move or share incomplete changes, generated output, untracked files, credentials, or task-local evidence implicitly between worktrees.
- Inspect tracked, untracked, ignored, and generated state before switching, integrating, or removing a worktree.
- Keep machine-specific worktree paths as local coordination state, not authoritative documentation or delivery status.
- Use remote task branches only for a real cross-device or collaboration need and under the applicable remote-write authorization.

## Integration and cleanup

- Re-check the current target, task branch, worktrees, contracts, implementation, tests, and validation evidence.
- Resolve mismatches and conflicts explicitly, then integrate dependent branches in dependency order using the project-authorized method.
- Rewrite only unpublished history within the approved scope. Do not rewrite shared history by default.
- Re-run proportionate validation when conflict resolution or cross-line interaction changes the evidence boundary.
- After integration, treat the target as authoritative; a task branch is execution history, not alternative current state.
- Remove a branch or worktree only after verifying that it contains no unique commit, untracked file, generated evidence, credential, unresolved conflict, or required handoff. Cleanup remains an authorized mutation.
- Retain recovery references only for an identified recovery need and review them after the new state is stable.

## Project-specific rules

A target project may define its integration branch, branch prefixes, maximum concurrent lines, validation gates, remote-branch policy, or stricter cleanup requirements. Keep those facts in the product repository and use this rule as the reusable baseline.
