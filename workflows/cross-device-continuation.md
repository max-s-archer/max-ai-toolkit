# Cross-Device Continuation Workflow

## Purpose

Resume work safely on another device when conversations, uncommitted product-repository changes, and local environment state are not shared automatically.

Use a separate, private development-state repository to transport concise task state and, only when needed, short-lived patches. It is synchronized working memory, not a second product repository.

## Boundaries

- The product repository remains the source of truth for product code, architecture, decisions, tests, releases, and committed history.
- The development-state repository holds current task state, references to product facts, and temporary patch transport artifacts.
- Do not copy full conversations into the development-state repository. Record only the decisions, evidence, unresolved questions, and next actions needed to resume safely.
- A patch is temporary transport, not alternative history. Bind it to an exact product-repository base commit and retire it after integration or abandonment.
- Do not store credentials, tokens, private keys, or other secrets in task state or patches.

## Recommended development-state repository layout

```text
<development-state-repository>/
- README.md
- projects/
  - registry.md
  - <project-id>/
    - project.md
    - author-todo.md
    - author-prompts.md
    - agent-proposals.md
    - active/<task-id>/
      - handoff.md
      - patches/
        - manifest.md
        - 001-<base-short-sha>.patch
    - archive/
- global/current-focus.md
- devices/<device-id>.md
```

`projects/registry.md` is a navigation index. Each `project.md` records stable continuation configuration such as the product repository locator, default branch, entry documents, and validation references. `author-todo.md`, `author-prompts.md`, and `agent-proposals.md` are private, non-authoritative working artifacts governed by the [Private Working-State Rule](../rules/common/private-working-state.md). Keep them only in the development-state repository; do not create local, ignored, empty placeholder, symbolic link, or mirrored copies in the product repository. Each active task has exactly one `handoff.md`; do not split its live state across status, next-task, and decision files. `global/current-focus.md` is only a convenience pointer and links to the authoritative task handoff.

## Workflow

### 1. Prepare the handoff on the source device

Check the product repository's branch, full `HEAD` commit, working-tree status, relevant diff, validation results, and source-device operating system and shell. Create or update `handoff.md` with [Development Handoff Template](../templates/development-handoff-template.md). Separate observed facts from inferences and proposed next actions. Follow [Cross-Platform Portability Rule](../rules/common/cross-platform-portability.md) for shared paths, commands, and diagrams.

If uncommitted changes must move between devices, create a patch and [Patch Manifest](../templates/patch-manifest-template.md). State exactly what the patch includes and excludes, including untracked, ignored, generated, or binary files. Do not claim it represents the whole working tree unless verified.

### 2. Publish resumable state

Commit and synchronize the development-state repository under its own access controls. Keep a handoff and its required patch artifacts in the same state-repository revision whenever practical. Synchronize private working-state artifacts only through this repository; do not create product-local copies for synchronization. Do not commit product code or product-local secrets to the state repository.

### 3. Verify the destination

Synchronize the development-state repository and read the selected `project.md`, `handoff.md`, and patch manifest. Identify the destination operating system and shell. Synchronize the product repository and inspect its remote, branch, `HEAD`, working tree, and referenced files.

Treat the handoff as a claim to verify, not a replacement for repository evidence. Do not treat a source-device command or path form as executable on the destination without confirming its portability or labeled destination environment. Stop and report a discrepancy when the product repository does not match the patch base, has conflicting work, or the patch coverage is insufficient.

### 4. Apply and validate a patch when authorized

Apply a patch only after a dry-run or equivalent compatibility check succeeds against its stated base. Re-check the resulting diff and run the focused validation in the handoff or manifest. If application or validation fails, preserve evidence and update the handoff; do not force, conceal partial application, or silently regenerate the patch.

### 5. Continue or close the task

Keep `handoff.md` current enough for the next deliberate device switch. When work is committed or abandoned, record the observable outcome and remove or archive the patch and manifest according to the state repository's retention rule.

## Completion criteria

- A receiving device identifies the intended project and task without the source conversation.
- The handoff records a verifiable baseline, evidence, scope, next action, and unresolved risks.
- Each patch has an explicit base commit, coverage, application method, and verification.
- Product facts remain in the product repository; transient state remains in the private development-state repository.
