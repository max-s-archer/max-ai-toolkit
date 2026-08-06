# Toolkit Consumption Model

## Purpose

Define how a product repository consumes `max-ai-toolkit` without copying it into the product repository or loading the whole Toolkit for every task.

## Model

`max-ai-toolkit` is an external, reusable method repository. A product repository remains the owner of its product facts, implementation, project-specific rules, and decisions.

Keep the Toolkit and product repository as independent repositories. At the start of a new product conversation, explicitly provide the Toolkit locator and require the agent to read the Toolkit bootstrap entry before reading task-specific product context. Do not rely on an agent discovering a sibling repository implicitly.

The locator may be a local path, a checked-out workspace location, or a deliberately pinned repository revision. Record the chosen locator or revision in the product repository's local agent instructions when reproducibility matters.

## Product-repository bootstrap contract

Create or update the product repository's `AGENTS.md` during bootstrap. It must:

1. Identify the Toolkit locator or approved reference.
2. Require a new agent session to read `<toolkit>/prompts/project-bootstrap.md` before project work.
3. Identify the product's own entry documentation, architecture, decisions, validation commands, and project-specific overrides.
4. State that the product repository overrides Toolkit guidance only explicitly and within the product's scope.

Use the following form in a new conversation, replacing the locator with the actual resolved path or reference:

```text
Read <toolkit-locator>/prompts/project-bootstrap.md first, then read this repository's AGENTS.md and the documents it routes to. Establish the required context before proposing or editing any project documentation or code.
```

## Progressive consumption

1. Read `prompts/project-bootstrap.md` and the product's `AGENTS.md`.
2. Read [Toolkit Architecture](architecture.md) and only the applicable policies.
3. Select the relevant role, workflow, skill, and template for the current task.
4. Read the product context required for that task.

Do not copy Toolkit rules into product documents unless the product needs an explicit, local override. Link to the Toolkit method or record the override's scope and reason instead.

## Version and update discipline

- Treat a Toolkit revision as part of the agent's working context when a task requires repeatability.
- Re-read affected Toolkit guidance when the product adopts a newer Toolkit revision or when a relevant Toolkit policy changes.
- Do not modify Toolkit content as an incidental side effect of product work. Extract a generalized improvement through a separate Toolkit change after removing product-specific facts.
