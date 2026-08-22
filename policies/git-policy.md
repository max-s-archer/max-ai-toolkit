# Git Policy

## Purpose

Maintain a trustworthy, readable Git history across Max's projects while leaving repository-specific implementation details to the relevant project and specialized Toolkit skills.

## Commit policy

- Write commit messages in English.
- Make each commit express one coherent, reviewable change. Do not combine unrelated implementation, formatting, generated output, and policy changes without a clear reason.
- Describe only changes supported by the staged content. Do not claim tests passed, bugs were fixed, or behavior changed without evidence.
- Follow an explicit project convention when it is more specific and does not conflict with this policy. Use the Conventional Commit Generator skill when a Conventional Commit message is required.

## Atomicity and repository consistency

- Make each commit an atomic, independently reviewable change: it should have one coherent purpose and be safe to understand, revert, or cherry-pick without relying on unrelated staged work.
- Atomicity does not mean one file or a small diff. Include the implementation, tests, and contract-document updates required for one coherent change in the same commit.
- Do not combine unconfirmed plans, temporary task state, unrelated cleanup, generated output, or separate behavior changes with an otherwise atomic change.
- After a commit, its implementation, tests, and authoritative documentation must not contradict one another. A contract document in that revision describes the confirmed state of that revision, not a pending or in-progress state.

## Branch and worktree policy

- Keep one authoritative integration branch unless a target project explicitly defines another model.
- Use short-lived, scope-based branches and isolated worktrees only when active work benefits from separation. Do not turn branches into competing project authority or durable delivery status.
- Serialize dependent or high-overlap work, and re-check contracts, implementation, tests, and validation evidence before integration.
- Follow the [Branch and Worktree Coordination Rule](../rules/git/branch-and-worktree.md). Keep project-specific naming, concurrency limits, and integration gates in the target repository.

## Release tag policy

- Use an annotated, immutable release tag. Do not overwrite, move, delete, or force-push an existing release tag.
- Use the project's documented release-version convention; use the `v`-prefixed Semantic Versioning form when no project convention exists.
- Keep the release tag, release version metadata, and tagged commit traceable to the same release intent.
- Write tag annotations, release notes, and other release-facing text in English.
- Obtain explicit confirmation before any remote write, including pushing a release tag. Use the Release Tag skill for validation and execution details.

## Repository integrity

- Do not commit secrets, credentials, private keys, personal tokens, or sensitive local configuration.
- Do not rewrite shared history or use force operations unless the author explicitly authorizes the exact operation and its scope.
- Preserve unrelated working-tree changes. Stop and report ambiguity rather than discarding, overwriting, or staging another person's work.
- Verify the observed repository state before reporting a commit, tag, push, merge, test, or release action as complete.
