# Documentation Policy

## Purpose

Treat documentation as an engineering asset: concise enough to use, specific enough to guide decisions, and maintained when the behavior or boundary it describes changes.

## Documentation ownership

- Keep Toolkit architecture, governance, reusable methods, templates, and Toolkit maintenance guidance in this repository.
- Keep product vision, requirements, architecture, roadmap, release information, and product-specific decisions in the corresponding product repository.
- Keep a product's ADRs in that product repository. Keep only reusable ADR guidance and an ADR template in the Toolkit.
- Keep Toolkit-specific decisions in Toolkit documentation when they affect this repository's long-term structure or governance.

## Documentation as part of change

Update relevant documentation in the same change when a change alters a public interface, operational workflow, policy, architectural decision, behavior that users or maintainers rely on, or an explicitly documented contract.

Do not create documentation merely to restate self-evident code or to record transient implementation detail. Prefer a short, durable explanation over an exhaustive narrative.

## Traceability and accuracy

- Record consequential decisions with their context, chosen direction, and meaningful trade-offs.
- Base statements about code, configuration, tests, release state, and execution results on available evidence.
- Do not present an unverified assumption, planned action, or inferred result as a completed fact.
- Mark examples, drafts, and deprecated material clearly so agents and maintainers do not treat them as current policy.

## Maintenance requirements

- Give each document one primary responsibility and a name that reflects its durable purpose.
- For a record series whose chronological order is part of its identity, use an append-only, zero-padded four-digit prefix such as `0001-adopt-offline-first-storage.md`. Never renumber, reuse, or repurpose an existing identifier.
- Apply ordered prefixes to ADRs and other decision or record series only when sequence is meaningful. Do not add numeric prefixes to ordinary guides, policies, skills, workflows, or templates merely for visual ordering.
- Link to the authoritative policy, rule, workflow, or template instead of duplicating its full content.
- Review references when moving, renaming, or replacing a document.
- Keep obsolete material only when it retains decision or migration value; otherwise remove it. Archived material must identify its replacement and should not be loaded as active guidance.
