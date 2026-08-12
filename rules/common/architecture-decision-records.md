# Architecture Decision Records

> Semantic source: English. Chinese counterpart: [architecture-decision-records.zh-CN.md](architecture-decision-records.zh-CN.md).

## Purpose

Define when an Architecture Decision Record (ADR) becomes authoritative, how proposals are handled before implementation, and how an implemented architecture decision remains traceable after replacement.

## ADR position

An ADR records a consequential architecture decision that has been implemented, accepted by the applicable author or architecture authority, committed, and synchronized to the designated shared Git history. It describes an architecture boundary that is active now or was active historically; it is not a pre-implementation proposal, approval request, implementation plan, or substitute for system architecture documentation.

Use an ADR when a decision has durable cross-component impact, is costly to reverse, affects data or compatibility, establishes ownership or dependency boundaries, or will require future maintainers to understand why the implemented system took this direction. Complete irreversibility is not required. Ordinary local implementation details and low-cost refactors do not require ADRs.

## Before implementation

Analyze a prospective architecture change in the authorized task or iteration, architecture review, technical assessment, or another explicitly non-authoritative working artifact. Record the problem, options, trade-offs, migration plan, risks, and author direction there. Do not create a proposed ADR or represent a selected-but-unimplemented direction as current architecture.

Author acceptance of a proposal authorizes only the scope explicitly granted. Implementation must still follow the applicable project workflow and validation requirements.

## Creating an active ADR

Create an ADR only after all of the following are true:

1. The consequential direction has been implemented.
2. Relevant migration and compatibility behavior has been validated or explicitly dispositioned.
3. The author or applicable architecture authority has accepted the implemented result and its material trade-offs.
4. The implementation and corresponding documentation have been committed and synchronized to the designated shared Git history.

An ADR created at that point has status `Active`. Link the implementation commits, validation evidence, and prior proposal or assessment where practical. Do not reconstruct certainty that the available evidence does not support.

## Status enumeration

Every ADR must use exactly one of these status values:

- `Active`: the recorded decision governs the current implemented architecture.
- `Inactive`: the decision governed an implemented architecture historically but no longer governs the current system.

Do not use `Proposed`, `Accepted`, `Superseded`, `Deprecated`, or another value as ADR status. Proposal state belongs to the pre-implementation artifact. Acceptance is a prerequisite for `Active`, not a separate ADR status. Replacement, removal, or loss of applicability is recorded as the reason for `Inactive`.

## Inactivating an ADR

Keep the existing ADR `Active` while a replacement is only planned or under implementation. Change it to `Inactive` only after the replacement or removal is implemented, accepted, committed, and synchronized.

An inactive ADR must record:

- the inactivation date;
- why it no longer governs;
- the replacing ADR when one exists;
- migration, compatibility, data, or downstream consequences; and
- any scope that remains historically applicable.

Create a new `Active` ADR for a consequential replacement and cross-link both records. Inactivation does not authorize reverting, deleting, or migrating implementation or data.

## Record integrity

- Use the target repository's append-only identifier sequence. Never renumber, reuse, or repurpose an ADR identifier.
- Preserve an inactive ADR as historical evidence; do not rewrite it to describe the replacement.
- Correct factual or link errors without changing historical meaning.
- Keep product-specific architecture facts and ADRs in the product repository. Keep this reusable method in the Toolkit.
