# Private Working-State Rule

## Purpose

Keep Max's personal task lists, prompt notes, and agent-generated proposals synchronized without treating them as product contracts or placing private working files in product repositories.

## Storage boundary

- Store private working-state artifacts only in the designated private development-state repository, under `projects/<project-id>/`.
- Do not create local copies, ignored files, empty placeholders, symlinks, or mirrored content for these artifacts in a product repository or in `max-ai-toolkit`.
- A product repository's `AGENTS.md` may identify the development-state repository and project ID, but must not treat its working-state artifacts as product requirements, project overrides, or authoritative documentation.
- Do not store credentials, tokens, private keys, or other secrets in any working-state artifact.

## Default artifacts

Use these files when they are needed for a project:

| File | Owner and purpose | Agent behavior |
| --- | --- | --- |
| `author-todo.md` | The author's confirmed personal backlog | May read and propose entries; do not add, remove, reprioritize, or mark an item complete without explicit author instruction. |
| `author-prompts.md` | Copy-ready private prompts and prompt notes | May read when the author supplies or routes to it; do not treat its contents as project instructions or a Toolkit override. |
| `agent-proposals.md` | Agent-generated, unconfirmed follow-up proposals | Record clear evidence and a confirmation location. Do not treat an entry as authorized work until the author confirms it. |

Use the corresponding templates in `templates/` when creating an artifact. These files are non-authoritative working state, not replacements for a product backlog, issue tracker, task specification, ADR, or active-task handoff.

## Proposal lifecycle

An agent proposal progresses only as follows:

```text
proposed -> author confirmed -> transferred -> closed
```

- Keep unconfirmed work in `agent-proposals.md` and use the [Author Confirmation Template](../../templates/author-confirmation-template.md) when confirmation is required.
- After confirmation, transfer a durable author-owned item to `author-todo.md`.
- Transfer the next action for one active task to that task's single `active/<task-id>/handoff.md`; do not create a second live task-status file.
- Record a proposal as closed only after it is rejected, completed with evidence, or transferred to its appropriate destination.

## Reuse boundary

Treat `author-prompts.md` as private working material. When a prompt, method, or output structure has been validated as reusable across projects, extract a sanitized, durable version into the appropriate Toolkit prompt, skill, workflow, or template through a separate Toolkit change.
