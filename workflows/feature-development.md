# Feature Development Workflow

## Purpose

Turn a confirmed product need into a small, reviewable, validated change while preserving product context and engineering boundaries.

## Inputs

- Feature request, expected user outcome, and acceptance criteria
- Target project context, applicable policies, and existing implementation
- Constraints, dependencies, and non-goals known to the author

## Workflow

### 1. Clarify the problem

Identify the user outcome, acceptance criteria, non-goals, affected users or systems, and unknowns. Inspect relevant project documentation and implementation. Ask for clarification before making a material product, scope, or architectural assumption.

### 2. Design the change

Identify affected boundaries, state ownership, interfaces, error handling, persistence, observability, and test implications as relevant to the project. Compare meaningful alternatives when trade-offs exist. Record a product-level decision when the change is consequential or difficult to reverse.

### 3. Plan an implementable slice

Define the smallest coherent implementation slice, changed components, validation approach, documentation impact, and completion criteria. Keep unrelated cleanup and speculative extensibility out of the feature change.

### 4. Implement with current context

Re-check the working tree and relevant files before writing. Implement the planned slice according to the target project's conventions. Preserve unrelated work and revise the plan when evidence exposes a material mismatch.

### 5. Validate behavior

Run the project's relevant automated checks and perform focused manual validation where automation is insufficient. For Android projects, use the project's configured build, test, lint, and device or emulator validation rather than assuming a universal command set.

### 6. Synchronize documentation

Update product documentation, decisions, user-facing text, or release notes when the feature changes a documented contract, workflow, or architectural boundary. Keep reusable lessons separate for later Toolkit extraction.

## Completion criteria

- Acceptance criteria and non-goals have been addressed or explicitly deferred.
- The implementation and validation evidence match the claimed outcome.
- Documentation and decision records reflect meaningful, durable changes.
- The final change is focused enough to review independently.
