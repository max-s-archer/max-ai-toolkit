# New Project Workflow

## Purpose

Initialize a new product repository with a clear product entry point, external Toolkit consumption, architecture and decision-record locations, and an evidence-based build and validation baseline.

## Inputs

- Product name, initial problem statement, intended users, and authorized scope
- Target repository location and Toolkit locator or approved Toolkit revision
- Known platform, distribution, privacy, compatibility, and delivery constraints
- Author decisions that are required before initialization can proceed

## Workflow

### 1. Establish the repository boundary

Create the product repository as an independent repository. Keep the Toolkit external; do not copy its methods into the product repository. Confirm the Toolkit locator that new agent sessions must use.

### 2. Create the product entry point

Create the product's public overview from [Project Overview Template](../templates/project-overview-template.md). Record the problem, product goal, current scope, non-goals, platform, and links to deeper documentation. Do not invent product facts that the author has not confirmed.

### 3. Create local agent routing

Create the product repository's `AGENTS.md` according to [Toolkit Consumption Model](../docs/consumption-model.md). It must route a new conversation to the external Toolkit bootstrap prompt, then to the product's own documents and project-specific rules.

### 4. Establish architecture and decision conventions

Identify the intended architecture-document location and ADR naming convention. Record these locations and their creation conditions in the project entry documentation or documentation map.

Create an architecture document only when confirmed system boundaries, dependencies, or technical direction exist. Create an ADR only when a consequential decision exists. Do not create empty placeholder documents, empty decision directories, or template-derived ADRs merely to complete the initial repository structure.

### 5. Establish build and validation baseline

Record the authoritative prerequisites and commands for build, test, lint, static analysis, and focused manual validation. For Android projects, record the actual Gradle tasks, supported SDK/device or emulator targets, and configured quality tools after they are chosen; do not assume a universal Android stack.

### 6. Plan the first vertical slice

Use [Requirements Analysis](../skills/requirements-analysis.md) and [Feature Development Workflow](feature-development.md) to define the first small, observable product capability. Identify its acceptance criteria, validation approach, and documentation impact.

### 7. Verify bootstrap readiness

Confirm that a new agent can resolve the Toolkit locator, read the required entry documents, understand the product boundary, run the documented validation baseline, and identify the first authorized task.

## Completion criteria

- The product has a public overview and a local `AGENTS.md` with an explicit Toolkit locator.
- Intended architecture and decision-record locations and their creation conditions are documented without representing unmade decisions as current evidence.
- Any initial architecture document or ADR is based on confirmed inputs or an accepted consequential decision.
- Build and validation instructions are based on the actual selected project configuration.
- The first vertical slice has a bounded scope and acceptance criteria.
- No project-specific facts have been added to the Toolkit.
