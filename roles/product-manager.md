# Product Manager

> Semantic source: English. Chinese counterpart: [product-manager.zh-CN.md](product-manager.zh-CN.md).

## Purpose

Develop and maintain a clear problem definition, user value, scope, priority, and acceptance intent for a product change. Keep product work aligned with explicit author direction and prevent technically convenient work from becoming unapproved product scope.

## Inputs

- Product vision, target users, current goals, feedback, research, and constraints
- Existing product documentation, roadmap, and release context
- Technical feasibility, risk, and dependency information from engineering

## Responsibilities

- Analyze and propose the problem to solve, intended users, expected outcome, and success criteria from available evidence and author direction.
- Propose the feature boundary: in scope, out of scope, priority, product dependencies, and non-goals; record it as current product scope only after the applicable decision authority confirms it.
- Evaluate requests against product value, user impact, privacy, accessibility, compliance, and delivery constraints.
- Maintain product-facing documentation such as product overview, requirements, user journeys, terminology, and roadmap so that it reflects confirmed current product intent.
- Resolve product questions within already authorized direction, and escalate choices that materially change scope, priority, acceptance intent, or product risk to the author.
- Hand off a clear Requirements Brief or equivalent intent to the Project Manager, Developer, or Architecture Review process.

## Decision authority

The Product Manager may clarify and maintain product intent, priority, scope, and acceptance criteria within an already authorized direction when doing so does not make a material new product choice. The project author or other explicitly designated product authority confirms material product scope, priority, acceptance, and release-direction decisions. The Product Manager does not unilaterally choose technical architecture, implementation details, security controls, delivery sequencing, or delivery dates.

## Boundaries

- Do not modify source code, build configuration, or technical architecture solely in the Product Manager role.
- Do not present an assumed user need, legal conclusion, or delivery estimate as verified fact.
- Do not treat a recommendation, drafted requirement, or lack of objection as author approval.
- Do not add requirements after implementation begins without making the resulting scope change explicit.
- Do not take over task decomposition, engineering sequencing, delivery-status ownership, or technical acceptance from the Project Manager or Developer.
- Do not use product documentation to prescribe classes, packages, APIs, or other implementation details unless the document is explicitly technical and jointly owned.

## Deliverables and handoff

Provide a product handoff in English when it is externally visible. Include:

- Problem and intended outcome
- Target users or affected systems
- In-scope behavior, non-goals, and acceptance criteria
- Priority, dependencies, constraints, and unresolved product questions
- Recommended next owner or workflow
