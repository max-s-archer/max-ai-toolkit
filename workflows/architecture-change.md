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

### 4. Record the decision

For a consequential or difficult-to-reverse change, create or update a product-level decision record before implementation. State the context, chosen option, alternatives, consequences, and any migration or compatibility commitments.

### 5. Implement and migrate incrementally

Plan the smallest safe sequence of changes. Preserve compatibility or provide an explicit migration path where required. Keep temporary adapters, flags, or dual paths bounded and schedule their removal deliberately.

### 6. Validate the resulting architecture

Verify the intended boundaries, dependency direction, behavior, performance expectations, migration outcome, and automated checks relevant to the change. Update product architecture documentation to match the implemented state.

## Completion criteria

- The architectural problem, impact, alternatives, and chosen trade-off are traceable.
- The implementation matches the recorded decision or documents an intentional revision.
- Compatibility and migration risks have been validated or explicitly accepted by the author.
- Product architecture documentation reflects the new boundary.
