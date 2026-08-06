# Release Workflow

## Purpose

Prepare, validate, tag, document, and hand off a release without treating a Git tag or release platform action as a substitute for release readiness.

## Inputs

- Confirmed release version and intended release scope
- Target commit and release branch
- Project-defined version source, validation requirements, and release destination
- Relevant changes since the previous release

## Workflow

### 1. Establish release intent

Confirm the version, target commit, release branch, and release scope. Read the project's release requirements and version source. Stop for clarification when the target, version, or authority to release is unclear.

### 2. Prepare the release candidate

Confirm that the implementation, documentation, version metadata, and release assets required by the project correspond to the intended release. Review the changed scope and outstanding known limitations.

### 3. Validate readiness

Run the project's required build, test, lint, static-analysis, and manual validation steps in proportion to release risk. Report completed, skipped, failed, and unavailable checks accurately. Do not turn a failed or unknown check into a release-ready claim.

### 4. Create and verify the tag

Use [Release Tag](../skills/release-tag.md) to validate the repository state, create an annotated release tag, generate release notes, obtain explicit approval for the remote write, and verify the pushed tag. Do not duplicate that skill's Git command details here.

### 5. Review release notes and platform publication

Review the English release notes for accuracy, scope, upgrade impact, and known limitations. The author reviews and approves publication on the release platform, including the selected tag and uploaded assets.

### 6. Record the outcome

Confirm the observable release result: version, tag, commit, validation summary, published location if applicable, and any follow-up work. Record only facts supported by evidence.

## Completion criteria

- The release version, commit, and tag are traceable to the same release intent.
- Required validation results are recorded accurately.
- Remote tag creation and platform publication occurred only with the required authorization.
- Release-facing text is in English.
- Unresolved limitations and follow-up work are visible to the author.
