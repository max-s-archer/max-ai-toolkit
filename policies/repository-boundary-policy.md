# Repository Boundary Policy

## Purpose

Keep `max-ai-toolkit` a reusable method repository and keep each product repository responsible for its own product reality.

## Ownership test

Classify content by the question it answers:

- Put content in `max-ai-toolkit` when it defines how to develop, review, document, release, or coordinate work across multiple projects without changing its core meaning.
- Put content in a product repository when it defines what that product is, why it exists, who it serves, how it is currently built, or what it should do next.

The practical question is: **Does this define how to develop any project, or how to develop this project?** Only the former belongs in the Toolkit.

## Toolkit responsibilities

The Toolkit may contain reusable principles, policies, agent rules, roles, skills, workflows, prompts, templates, maintenance documentation, and sanitized examples.

The Toolkit must not contain a product's vision, requirements, roadmap, module map, implementation-specific architecture, current iteration state, source code, release assets, or project-level decision records.

## Product repository responsibilities

Each product repository owns its README, product and technical documentation, architecture, ADRs, backlog, release history, implementation, tests, and project-specific operating rules.

A product repository may add more specific rules for its own scope. It must state the scope and reason for any override; it must not alter Toolkit files merely to suit one product.

## Reuse and extraction

- Reference a Toolkit method from a product instead of copying it when the method is unchanged.
- Extract an experience into the Toolkit only after removing product-specific facts and confirming that it is useful beyond one project.
- Keep product examples out of the Toolkit unless they are intentionally sanitized and clearly presented as examples.
- Return reusable improvements to the Toolkit through a dedicated Toolkit change, not as an incidental product-repository edit.
