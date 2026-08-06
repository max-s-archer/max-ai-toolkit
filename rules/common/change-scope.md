# Change Scope Rule

## Purpose

Make the smallest safe change that satisfies the authorized request while preserving unrelated work and respecting project-specific ownership.

## Before editing

- Confirm the target repository, requested outcome, and files or systems in scope.
- Inspect the current working-tree status, current branch or revision when relevant, and the existing content that will be changed.
- In a shared or multi-terminal environment, re-check the relevant files and repository state immediately before editing or performing a write action. Treat a difference between the current state and the user's prompt as a discrepancy to resolve, not as permission to overwrite.
- Read applicable project instructions and conventions before applying Toolkit methods.

- For a cross-device patch, verify the patch manifest's product repository, base commit, coverage, and expected destination working-tree state before applying it.

## While editing

- Change only what is necessary for the requested outcome.
- Preserve unrelated, pre-existing, or concurrently created modifications.
- Do not reformat, rename, regenerate, stage, revert, or delete unrelated material as a side effect.
- Keep project-specific overrides explicit and local to the project. Do not alter a reusable Toolkit method solely to serve one project.

- Do not force, partially apply without recording, or silently regenerate a patch when its base or coverage differs from the observed repository state.

## When scope is unclear

- Inspect available context first.
- Ask the author before expanding the task to additional components, repositories, external systems, destructive actions, or broad refactors.
- Stop and report a conflict when concurrent changes, unclear ownership, or a changed repository state makes a safe targeted edit impossible.

## Before reporting completion

- Review the final changed state against the authorized request.
- Validate the change in proportion to its risk and report what was actually checked.
- Leave staging, committing, pushing, and other external actions to their separately authorized workflows.
