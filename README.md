# max-ai-toolkit

[Chinese (Simplified)](README.zh-CN.md)

Personal AI-agent engineering methods for Max's GitHub projects.

`max-ai-toolkit` is a public, personal method repository. It provides reusable AI-agent development infrastructure rather than product requirements or implementation. It is optimized for Max's project ecosystem, not general-purpose use.

## Start here

1. Read the [Toolkit Architecture](docs/architecture.md) for scope, structure, precedence, and the progressive loading model.
2. Read [AGENTS.md](AGENTS.md) for the minimum agent routing and change protocol.
3. Load only the policies, rules, roles, workflows, skills, templates, and project context required for the current task.
4. Read the target project's own documentation and explicit rules before making project changes.

## Repository map

| Area | Use |
| --- | --- |
| [`policies/`](policies/) | Cross-project governance and requirements |
| [`skills/`](skills/) | Reusable methods for focused tasks |
| [`roles/`](roles/) | Agent responsibility definitions |
| [`docs/`](docs/) | [Architecture](docs/architecture.md) and [migration guidance](docs/migration-guide.md) for this Toolkit |
| `principles/`, `rules/`, `workflows/`, `prompts/`, `templates/` | Created as validated, reusable content is added |

## Language

English is the public default. Chinese is used where it improves Max's internal maintenance experience, and bilingual documents are maintained only when they provide sustained value. See the [Language Policy](policies/language-policy.md).

## Reading order

Use progressive loading: Toolkit architecture and applicable policy first; then the current role or workflow; then only the needed skill or template; finally the relevant project context. The full precedence order is defined in the [Toolkit Architecture](docs/architecture.md#document-precedence).
