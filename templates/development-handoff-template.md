# Development Handoff Template

## Use

Use one copy for each active task at `projects/<project-id>/active/<task-id>/handoff.md` in a private development-state repository. It is a concise synchronized working-state record; it does not replace product documentation, an ADR, Git history, or direct repository inspection.

Replace placeholders with observed facts. Remove inapplicable sections; do not invent missing information.

---

# Handoff: <Task Title>

## Identity

- Project ID: `<project-id>`
- Task ID: `<task-id>`
- Status: `<active | paused | blocked | closed>`
- Last updated: `<UTC timestamp>`
- Updated on: `<device-id or environment>`

## Objective and Boundary

- Objective: <Intended outcome>
- In scope: <Authorized work>
- Out of scope: <Explicit non-goals>

## Verified Product-Repository Baseline

- Remote: `<remote URL or configured remote name>`
- Branch: `<branch>`
- HEAD: `<full commit SHA>`
- Working tree at handoff: `<clean | changed; summarize observed files>`
- Relevant product documents and decisions: <Links or paths>

## Completed Work and Evidence

- <Completed action and supporting evidence>

## Current State and Next Action

- Current state: <What is true now>
- Next action: <Smallest next action>
- Required validation: <Command, check, or focused manual validation>

## Decisions, Assumptions, and Questions

- Confirmed decision: <Decision and link to the authoritative product record>
- Assumption or inference: <Clearly labeled item>
- Open question or blocker: <Question, owner, and why it matters>

## Patch Transfer

- Patch status: `<none | pending | applied | retired>`
- Manifest: `<relative path or none>`
- Coverage or exclusions: <What the patch does and does not carry>

## Resume Notes

<Information the receiving device must verify or must not do.>
