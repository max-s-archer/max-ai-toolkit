# Project Bootstrap Prompt

> Semantic source: English. Chinese counterpart: [project-bootstrap.zh-CN.md](project-bootstrap.zh-CN.md).

Use this prompt to start an agent session for a new product project. Replace `<toolkit-locator>` with the confirmed local Toolkit path or revision before use.

Establish the following context before editing project documentation, code, Git state, or remote resources:

1. Read `<toolkit-locator>/docs/consumption-model.md`.
2. Read `<toolkit-locator>/workflows/new-project.md`.
3. Read `<toolkit-locator>/AGENTS.md`, then load only the policies, roles, workflows, skills, and templates it routes to.
4. Read the target project's `AGENTS.md`. If it does not exist, follow the New Project Workflow; first ask the author to confirm the target repository and Toolkit locator.
5. Read the target project's existing README, architecture documentation, ADRs, and build/validation guidance. Read only the material relevant to the current initialization or task.

## Language handling

- A document ending in `.zh-CN.md` is a Chinese language counterpart of the corresponding unsuffixed document.
- Read either language, or compare both languages, when doing so improves understanding.
- When the two versions have the same intended meaning, treat the unsuffixed English document as authoritative.
- Report any material semantic difference between a language counterpart and its English source. Do not treat a translation as a project-specific override.

Before any write action, provide a concise Context Summary that states:

- Toolkit and project documents read
- Toolkit locator or revision
- Current product goal, known scope, and unresolved items
- Available build and validation baseline, or missing configuration
- Recommended role, workflow, skill, and template
- Author confirmation still required before work begins

If the Toolkit locator, target project path, product intent, or required authorization is missing, ask for clarification. Do not guess or create files.
