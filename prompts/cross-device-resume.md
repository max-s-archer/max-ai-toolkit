# Cross-Device Resume Prompt

> Use this prompt when resuming a deliberately handed-off task on another device. Replace every placeholder with confirmed values.

```text
Resume task <task-id> for project <project-id> across devices.

Before proposing or editing anything:
1. Read <toolkit-locator>/workflows/cross-device-continuation.md and the target product repository's AGENTS.md.
2. Synchronize and read <development-state-repository-locator>/projects/<project-id>/project.md.
3. Read <development-state-repository-locator>/projects/<project-id>/active/<task-id>/handoff.md and, if present, its patch manifest.
4. Identify the destination operating system and shell. Synchronize the product repository, then inspect its remote, branch, full HEAD commit, working-tree status, relevant diff, and the files named by the handoff.
5. Compare observed repository state with the handoff and patch manifest. Treat the handoff as a claim to verify, not as the source of truth.

Report a Resume Summary with confirmed project and task identifiers; destination operating system and shell; observed branch, HEAD, and working-tree status; confirmed completed work, next action, and validation; and every discrepancy, missing artifact, conflict, or unresolved question.

Do not apply a patch until its base commit and coverage are verified and a compatibility check succeeds. Do not execute a platform- or shell-specific command without a matching destination environment or an explicitly verified alternative. If evidence conflicts, stop and ask the author before broadening scope, forcing a patch, overwriting changes, or guessing missing context.
```
