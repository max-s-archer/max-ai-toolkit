# Migration Guide

## Purpose

Use this guide when moving existing material into or out of `max-ai-toolkit`, extracting reusable knowledge from a product project, reorganizing Toolkit content, or retiring obsolete guidance.

This is a maintenance guide, not default task context. Do not load it unless the work involves classification, migration, consolidation, archival, or removal.

## Classify before moving

Answer these questions for every candidate document or asset:

1. Is it tied to one product's name, requirements, module structure, architecture, roadmap, iteration, or implementation state?
2. Can another project reuse it without changing its core meaning?
3. Does it define a principle, policy, rule, role, skill, workflow, prompt, template, Toolkit documentation, example, script, or archive record?
4. Is it stable enough for formal guidance, or is it still an experiment or working note?
5. Is it public-facing, reusable, internal-only, or private?
6. Does an agent need it by default, only for a specific task, or never as active context?
7. Does an authoritative version already exist elsewhere?
8. Can the material be made smaller, clearer, or more narrowly responsible before it is moved?

## Choose a destination

| Content | Destination |
| --- | --- |
| Product vision, requirements, architecture, ADRs, roadmap, implementation, releases | The relevant product repository |
| Durable engineering rationale | `principles/` |
| Cross-project requirements and governance | `policies/` |
| Specific agent execution constraints | `rules/` |
| A responsibility, perspective, and handoff boundary | `roles/` |
| A repeatable method for a focused professional task | `skills/` |
| A multi-stage process | `workflows/` |
| A task entry point that composes existing assets | `prompts/` |
| A reusable output structure | `templates/` |
| Information about maintaining this Toolkit | `docs/` |
| A sanitized demonstration of use | `examples/` |
| Reproducible maintenance automation | `scripts/` |
| Superseded material with continuing historical value | `archive/` |

If the content does not have a durable, reusable purpose, keep it in a private working space, a product repository, or an experimental playground rather than creating a new Toolkit category.

## Migration workflow

1. **Inventory** — Identify the source, current owner, intended users, and any inbound references.
2. **Classify** — Use the questions and destination table above. Stop when ownership is unclear and resolve the boundary before moving files.
3. **Extract or return** — Remove product-specific facts from reusable material, or return product-specific material to its product repository.
4. **Consolidate** — Choose one authoritative document. Replace duplicated prose with links to the authority.
5. **Normalize** — Use lowercase kebab-case names, the correct directory, and the language rules in the [Language Policy](../policies/language-policy.md).
6. **Validate** — Apply the quality standard and migration checklist below; verify links and affected references.
7. **Retire safely** — Delete material with no remaining value. Archive only material that has a clear replacement or meaningful migration/decision value.

## Quality standard

Material entering a formal Toolkit area must:

- Have one primary responsibility and a durable, descriptive filename.
- State its scope, inputs and outputs, or behavioral boundary as appropriate to its type.
- Avoid unstated dependency on a particular product.
- Avoid duplicating the authoritative content of another Toolkit document.
- Be clear enough for an agent to follow and a maintainer to review.
- Use evidence for claims about execution, code, tests, releases, or results.
- Contain no secrets, private data, or sensitive local configuration.
- Follow the public-English and bilingual-consistency requirements when externally visible.

## Maturity stages

### Stage 1 — Personal Foundation

Build a small, coherent set of policies, skills, and documentation that supports Max's active projects. Favor Chinese internal efficiency where appropriate. Keep the repository compact and validate guidance through real use.

### Stage 2 — Reusable Toolkit

Extract methods that have worked across multiple projects. Compose prompts from existing roles, skills, workflows, and templates. Add focused maintenance checks to prevent drift and duplication.

### Stage 3 — Public Toolkit

Maintain English public entry points, complete public examples, clear boundaries between reusable and private material, and an understandable release/change history. Do not adopt this maintenance cost before the content has demonstrated public value.

## Migration checklist

- [ ] The content has been classified using the ownership test.
- [ ] Product-specific material has been returned to the relevant product repository.
- [ ] Reusable material contains no product facts that change its core meaning.
- [ ] The destination directory matches the content's primary responsibility.
- [ ] An existing authoritative document has been reused or linked instead of duplicated.
- [ ] The filename uses lowercase kebab-case, no temporary version labels, and an append-only numeric prefix only when the record series has meaningful chronological identity.
- [ ] The document's language and any bilingual counterpart comply with the Language Policy.
- [ ] Links, references, and navigation have been updated.
- [ ] Agents will not load obsolete, archived, or task-irrelevant material by default.
- [ ] The change has been reviewed for secrets, private data, and unsupported claims.
- [ ] Replaced material has been deleted or archived with a replacement and reason.
- [ ] The resulting change is small enough to review and validate independently.
