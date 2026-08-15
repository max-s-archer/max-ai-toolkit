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

## Planned locations and document creation

A planned document location defines a future responsibility, not an existing conclusion, contract, or source of authority. An entry document or documentation map may identify a planned path, its intended responsibility, and the condition under which it should be created.

Create an authoritative document only when confirmed inputs, evidence, or an authorized decision exist for its responsibility. Do not create empty architecture, validation, security, privacy, decision, release, or similar documents merely to complete a planned repository structure.

Do not link to a planned path as though it were a current authoritative document. When an applicable document is created, give it one confirmed responsibility and ensure that its statements describe the active contract for the repository revision. Keep unresolved questions, exploratory work, and proposed content in non-authoritative working artifacts until they are confirmed.

## Contract documents and working state

Treat an authoritative product or Toolkit document as a contract for the repository revision in which it appears. It must describe confirmed, active facts, requirements, decisions, boundaries, and validation expectations; do not present pending approval, in-progress discussion, or proposed future state as current contract.

Keep proposed work, open questions, iteration progress, temporary investigation notes, and device-handoff state in explicitly non-authoritative working artifacts such as a task list, iteration document, issue, or private development-state record. These artifacts may link to a contract document but must not silently change it.

An [author annotation](../rules/common/author-annotations.md) is a narrow source-level exception for a bounded review or change request beside its target text. It remains non-authoritative, must use an HTML comment, and must be removed or transferred to the designated private working state when it is resolved or becomes durable. Do not commit an unresolved annotation as part of an authoritative document.

When a draft is necessary, identify it explicitly as a draft and ensure entry documents and agent routing do not treat it as authoritative. Promote a draft to a contract document only when its content has been confirmed for the relevant repository revision.

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
