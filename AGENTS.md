# Agent Routing

## Read progressively

1. Read [docs/architecture.md](docs/architecture.md).
2. Read the applicable document in `policies/`.
3. Read the target project's entry documentation and explicit instructions.
4. Load only the role, workflow, skill, template, and implementation context required for the task.

Do not load the entire Toolkit by default. Do not treat templates, examples, or archived material as active policy.

When creating or modifying shared documentation, command guidance, paths, scripts, or low-fidelity diagrams, load `rules/common/cross-platform-portability.md`.

## Select task assets

| Task | Load |
| --- | --- |
| New product repository | `prompts/project-bootstrap.md`, `workflows/new-project.md`, and the project-overview template |
| Feature or ambiguous request | Requirements Analysis, Feature Development Workflow, and the relevant product context |
| Bug | Bug-Fix Workflow and the relevant reproduction evidence |
| Consequential architecture change | Architecture Review, Architecture Change Workflow, and relevant ADRs |
| Release | Release Workflow, Release Tag, and Release Notes Template |
| Collaboration or governance review | Engineering Governance Reviewer and the applicable project and Toolkit context |
| Role boundary or authorization question | `roles/authorization-matrix.md` and the applicable role definitions |
| Cross-device task continuation | `rules/common/cross-platform-portability.md`, `prompts/cross-device-resume.md`, `workflows/cross-device-continuation.md`, and the applicable development-state handoff and patch manifest |
| Private working state | `rules/common/private-working-state.md` and the applicable author-todo, author-prompts, or agent-proposals template |
| Commit or push | `rules/git/commit-and-push.md` and Conventional Commit Generator |

Load only the assets that apply. Use the [Toolkit Consumption Model](docs/consumption-model.md) when entering a product repository from this external Toolkit.

## Resolve conflicts

Follow this precedence order:

1. System and safety instructions
2. Explicit target-project rules
3. Toolkit policies
4. Toolkit rules
5. Active workflow
6. Active role
7. Active skill
8. Active prompt
9. Templates and examples

Apply a project override only when it is explicit, scoped, and compatible with higher-priority instructions.

## Before changing files

- Confirm whether the task belongs to this Toolkit or to a product repository.
- Inspect relevant existing files and conventions before editing.
- Keep changes focused on the requested scope; preserve unrelated work.
- Do not infer unverified facts or report unperformed actions as complete.
- Update relevant documentation when a documented contract, workflow, policy, or architecture boundary changes.

## Repository boundary

Use this repository for reusable methods. Keep product vision, requirements, implementation details, product architecture, product ADRs, roadmap, and release assets in the product repository. Read [policies/repository-boundary-policy.md](policies/repository-boundary-policy.md) when ownership is uncertain.
