# Architecture Change Workflow

## Purpose

Make consequential structural changes deliberately: understand their impact, compare viable options, record the decision, implement safely, and validate the resulting boundaries.

## Inputs

- Problem statement and reason the current architecture is insufficient
- Affected product boundaries, constraints, and non-functional requirements
- Existing architecture, decisions, dependencies, and migration constraints

## Workflow

### 1. Assess the current boundary

Describe the current responsibility, dependency, data-flow, state-ownership, and lifecycle boundaries relevant to the problem. Identify the concrete limitations and the cost of leaving them unchanged.

### 2. Map impact

Identify affected modules, interfaces, data, persistence, tests, build configuration, operations, migration paths, and compatibility obligations. Distinguish direct impact from assumptions that require validation.

### 3. Compare options

Define the viable options, including retaining the current design when appropriate. Compare trade-offs in complexity, correctness, performance, maintainability, delivery risk, migration cost, and reversibility. Do not select an option merely because it is newer or more abstract.

### 4. Obtain direction and record the proposal

For a consequential or difficult-to-reverse change, record the problem, options, selected direction, consequences, and migration or compatibility commitments in the authorized task, iteration, architecture review, technical assessment, or another explicitly non-authoritative working artifact. Obtain the required author or architecture-authority direction before implementation. Do not create an ADR for an unimplemented proposal.

### 5. Implement and migrate incrementally

Plan the smallest safe sequence of changes. Preserve compatibility or provide an explicit migration path where required. Keep temporary adapters, flags, or dual paths bounded and schedule their removal deliberately.

### 6. Validate the resulting architecture

Verify the intended boundaries, dependency direction, behavior, performance expectations, migration outcome, and automated checks relevant to the change. Update product architecture documentation to match the implemented state.

### 7. Record the active architecture decision

After the implemented result and material trade-offs are accepted, committed, and synchronized, create an `Active` ADR when the decision meets the consequential-decision threshold. Follow [Architecture Decision Records](../rules/common/architecture-decision-records.md). If the change replaces an active ADR, keep the earlier record active until the replacement is effective, then mark it `Inactive` and cross-link the records.

## Completion criteria

- The architectural problem, impact, alternatives, and chosen trade-off are traceable.
- The implementation matches the authorized direction or documents an intentional revision.
- Compatibility and migration risks have been validated or explicitly accepted by the author.
- Product architecture documentation reflects the new boundary.
- Every applicable ADR records an implemented, accepted, committed, and synchronized architecture fact.
