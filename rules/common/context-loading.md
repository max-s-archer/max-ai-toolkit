# Context Loading Rule

## Purpose

Load the smallest reliable context required for the current task. Avoid treating the entire Toolkit, a whole repository, or every available document as default context.

## Loading order

Load information progressively in this order:

1. **Bootstrap** — Identify the target repository. Read its entry instructions, this Toolkit's architecture, and the policies applicable to the task.
2. **Role and workflow** — Load the active role and workflow only when the task requires their responsibility model or multi-stage process.
3. **Skill and template** — Load the focused skill, template, or reference needed for the requested professional action or output.
4. **Project context** — Read the relevant project overview, architecture, decisions, task details, source files, configuration, and tests.

## Selection rules

- Prefer the most specific, authoritative, and current source available.
- Read the target project's explicit instructions before applying general Toolkit guidance.
- Load a document only when it affects the requested decision, execution, validation, or output.
- Read referenced material on demand; do not recursively load every linked document.
- Do not treat templates, examples, archived material, or unrelated project files as active requirements.

## Project-specific overrides

Apply an explicit target-project rule before the Toolkit guidance it replaces, subject to higher-priority system and safety requirements. Treat a project rule as an override only when the project's `AGENTS.md` routes to it and it identifies the replaced Toolkit guidance, replacement rule, scope, and reason.

When project material suggests a different rule but does not explicitly establish an override, inspect the relevant project instructions and source material first. If the conflict or scope remains unresolved, ask the author before proceeding. Do not treat an unlinked private prompt, an implied preference, or a missing statement as permission to override Toolkit guidance.

## Cross-device continuation

When resuming a task from another device and the product's `AGENTS.md` identifies a development-state repository, read only the relevant project configuration, task handoff, and patch manifest from that repository. Then verify the reported branch, commit, working-tree state, and referenced files in the product repository. Treat synchronized task state as a lead, not as evidence that overrides the current repository.

## When context is insufficient

State what is missing and why it matters. Inspect the relevant source when it is available; otherwise ask for clarification before making an assumption that would broaden scope, change ownership, or cause an irreversible action.
