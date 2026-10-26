# Commit and Push Rule

## Purpose

Create a trustworthy Git commit or push only after the changed state, commit message, authorization, and remote target have been verified.

## Short trigger

Resolve `提交检查` and `提交` through
[Short Triggers](../../prompts/short-triggers.md).
This rule remains authoritative for the commit threshold, review,
and authorization boundary.

## Before creating a commit

- Confirm explicit author authorization to create a commit. A request to generate a message, inspect a diff, or prepare files is not authorization to commit.
- Inspect the current branch or revision, working-tree status, and relevant diff.
- Inspect the staged diff and staged file list. Confirm that they contain only the intended, authorized change.
- Confirm that the staged change is atomic: it has one coherent purpose, excludes unrelated cleanup and temporary working state, and includes any implementation, tests, and contract-document updates needed to keep the staged revision internally consistent.
- When an authoritative document is staged, verify that it describes the confirmed state introduced or retained by the staged revision, rather than a pending approval, proposal, or in-progress task.
- Stop and report unrelated, concurrent, untracked, or ambiguous changes rather than staging, discarding, or including them by default.
- Run the applicable validation and record only the checks that actually completed.
- Generate the commit message from the staged content using [Conventional Commit Generator](../../skills/conventional-commit-generator.md) when Conventional Commits apply. Review the generated message against the staged diff before committing; do not commit an unchecked or unsupported message.

## Creating and verifying a commit

- Create one atomic, coherent, reviewable commit that matches the authorized scope.
- Verify the resulting commit identifier, subject, changed files, and relevant diff before reporting success.
- Report validation performed, omitted checks, and remaining limitations accurately.

## Before pushing

- Confirm the exact remote, branch or ref, and push command.
- Obtain explicit author authorization for the specific remote write. Commit authorization does not imply push authorization.
- Re-check the repository state when another terminal, agent, or contributor may have changed it since commit verification.
- Never force-push, rewrite shared history, or push secrets or unrelated work without explicit authorization and a documented exceptional reason.

## After pushing

- Verify the remote result using available evidence.
- Report the pushed reference, commit or tag, and any failure or unresolved discrepancy.
