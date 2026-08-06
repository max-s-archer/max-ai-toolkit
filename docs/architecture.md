# Toolkit Architecture

## Purpose

`max-ai-toolkit` is Max's personal method repository for AI-agent engineering. It provides reusable development infrastructure—principles, policies, rules, roles, skills, workflows, prompts, templates, and maintenance documentation—for projects under Max's GitHub account.

The repository is public but optimized for Max's working context and project ecosystem. It is a method repository, not a generic prompt collection or a product description.

Its governing question is: **How should an agent help develop any project?** A product repository instead answers: **What is this product, and how should this product be developed?**

## Design characteristics

- Prefer durable, reusable methods over one-off prompts.
- Keep guidance explicit, structured, concise, and adequate for reliable agent execution.
- Keep product-specific implementation facts in the consuming project.
- Make requirements auditable where practical; do not depend on hidden reasoning or unsupported claims.
- Preserve a consuming repository's more specific conventions when they do not conflict with higher-priority instructions.

## Repository boundary

The Toolkit owns reusable engineering methods and agent guidance. Product repositories own product vision, requirements, architecture, decisions, roadmap, implementation, tests, and releases.

Do not store a product's module structure, iteration state, product ADRs, or release assets in the Toolkit. Do not modify a Toolkit method merely to accommodate one product; use an explicit, local project override instead.

Read the [Repository Boundary Policy](../policies/repository-boundary-policy.md) for the full ownership test.

## Stable structure

The Toolkit keeps a small set of responsibility-based top-level areas. A directory is created only when it contains real, maintained content.

| Area | Responsibility |
| --- | --- |
| `principles/` | Long-lived engineering values and decision rationale |
| `policies/` | Cross-project requirements and governance constraints |
| `rules/` | Executable agent behavior constraints |
| `roles/` | Agent responsibilities, perspective, and handoff boundaries |
| `skills/` | Reusable methods for a focused professional task |
| `workflows/` | Multi-stage processes that compose roles and skills |
| `prompts/` | Task entry points that compose existing assets |
| `templates/` | Standard output structures |
| `agents/` | Validated agent definitions or orchestration configurations |
| `docs/` | Documentation about the Toolkit itself |
| `examples/` | Sanitized demonstrations of Toolkit use |
| `scripts/` | Repository-maintenance automation |
| `archive/` | Replaced material retained for historical or migration value |

Do not add a top-level directory merely because content volume grows. First determine whether the content has a new long-term responsibility or belongs within an existing area.

## Document precedence

Resolve conflicting guidance in this order:

1. Current system and safety instructions
2. Explicit rules of the target project
3. Toolkit policies
4. Toolkit rules
5. The active workflow
6. The active role
7. The active skill
8. The active prompt
9. Templates and examples

A project may override a Toolkit policy only when the override is explicit, scoped to that project, and does not conflict with higher-priority instructions.

## Agent loading model

Load context progressively. Do not read the entire Toolkit by default.

1. **Bootstrap** — Read this architecture document, the relevant public policy, and the target project's entry documentation.
2. **Role and workflow** — Load the role and workflow required for the task, if any.
3. **Skill and template** — Load only the specialized skills and output templates needed to complete the task.
4. **Project context** — Read the product's relevant overview, architecture, decisions, task context, and implementation artifacts.

Before making a change, confirm the target repository, applicable scope, existing conventions, and whether the requested work affects a documented contract. Keep changes narrow and update documentation when its documented behavior or boundary changes.

## Related policies

- [Language Policy](../policies/language-policy.md)
- [Repository Boundary Policy](../policies/repository-boundary-policy.md)
- [Documentation Policy](../policies/documentation-policy.md)
- [Git Policy](../policies/git-policy.md)

## Related maintenance guidance

- [Migration Guide](migration-guide.md)
