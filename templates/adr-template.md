# Architecture Decision Record Template

## Use

Create ADRs in the target product repository when a decision is consequential, difficult to reverse, or needed to preserve architectural context. This Toolkit provides the method and template; it does not own product ADRs.

Name each record with the next four-digit sequence number and a concise lowercase kebab-case title:

```text
docs/decisions/0001-adopt-offline-first-storage.md
```

The sequence belongs to the target repository. Append the next number; never renumber, reuse, or repurpose an existing ADR identifier. Once an ADR is accepted, preserve it as a historical decision. Record a changed decision in a new ADR that explicitly supersedes the earlier record.

---

# ADR-0001: <Decision Title>

## Status

Accepted

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

## Supersedes

None
