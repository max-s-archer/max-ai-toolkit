# Architecture Decision Record Template

> Semantic source: English. Chinese counterpart: [adr-template.zh-CN.md](adr-template.zh-CN.md).

## Use

Create ADRs in the target product repository only for implemented architecture decisions that satisfy [Architecture Decision Records](../rules/common/architecture-decision-records.md). Use an authorized task, iteration, architecture review, or technical assessment for a pre-implementation proposal. This Toolkit provides the method and template; it does not own product ADRs.

Name each record with the next four-digit sequence number and a concise lowercase kebab-case title:

```text
docs/decisions/0001-adopt-offline-first-storage.md
```

The sequence belongs to the target repository. Append the next number; never renumber, reuse, or repurpose an existing ADR identifier. Preserve inactive ADRs as historical decisions. Record a consequential replacement in a new ADR, then make the earlier ADR inactive only after the replacement is implemented, accepted, committed, and synchronized.

---

# ADR-0001: <Decision Title>

## Status

- Value: `Active`
- Updated: YYYY-MM-DD
- Basis: <Author or architecture-authority acceptance, synchronized implementation and documentation evidence>

## Date

YYYY-MM-DD

## Context

Describe the problem, constraints, affected boundaries, and why a decision is required now.

## Decision

State the chosen direction precisely enough to guide implementation and review.

## Rationale

Explain why this option best fits the current context and constraints.

## Considered Options

### <Option A>

- Benefits:
- Trade-offs:

### <Option B>

- Benefits:
- Trade-offs:

## Consequences

Describe expected positive, negative, operational, compatibility, migration, and maintenance consequences.

## Implementation Notes

Record the required migration path, compatibility plan, or follow-up work when applicable.

## Implementation and Validation Evidence

- Implementation commits:
- Synchronized documentation:
- Validation or accepted gaps:
- Prior proposal or assessment:

## Replaces

None

## Inactivation

- Date: Not applicable while `Active`
- Reason: Not applicable while `Active`
- Replaced by: None
- Consequences: None
