# Agent Routing

## Read progressively

1. Read [docs/architecture.md](docs/architecture.md).
2. Read the applicable document in `policies/`.
3. Read the target project's entry documentation and explicit instructions.
4. Load only the role, workflow, skill, template, and implementation context required for the task.

Do not load the entire Toolkit by default. Do not treat templates, examples, or archived material as active policy.

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
