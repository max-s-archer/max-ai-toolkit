# Role Authorization Matrix

> Semantic source: English. Chinese counterpart: [authorization-matrix.zh-CN.md](authorization-matrix.zh-CN.md).

## Purpose

Provide a single visual index of the normal authority and escalation boundaries among the project author, Product Manager, Project Manager, Developer, and Engineering Governance Reviewer. This matrix summarizes the linked role definitions; it does not replace them, grant task authorization, or override a target project's explicit rules.

## Legend

- `Confirm`: makes or explicitly accepts the consequential decision.
- `Execute`: may act within an already authorized scope without per-step confirmation.
- `Recommend`: analyzes and proposes but does not approve or execute by role alone.
- `Evidence`: supplies observed facts, risks, or validation results.
- `Separate authorization`: requires explicit authorization for the specific action even when related work is authorized.
- `No role authority`: the role neither approves nor performs the action solely by holding that role.

## Matrix

| Activity or decision | Project author | Product Manager | Project Manager | Developer | Engineering Governance Reviewer |
| --- | --- | --- | --- | --- | --- |
| Material product direction, scope, priority, or acceptance change | Confirm | Recommend; maintain after confirmation | Surface delivery impact | Supply feasibility evidence | Review authority clarity and proportionality |
| Product clarification within confirmed direction | Available for escalation | Execute | Coordinate when delivery is affected | Supply technical evidence | Recommend only when governance is affected |
| Create or materially change delivery scope | Confirm | Recommend product boundary | Recommend plan and impact | Supply estimate and risk evidence | Review authorization boundary |
| Decompose and sequence authorized work | Set constraints or override when needed | Supply product priority | Execute | Supply dependencies and estimates | Recommend only when governance is affected |
| Maintain delivery status and coordinate handoffs | Receive evidence and make required trade-offs | Supply product decisions | Execute | Supply implementation and validation status | Review status rules and handoff clarity |
| Choose reversible local implementation details | No routine involvement | No role authority | No role authority | Execute | No role authority |
| Consequential architecture or compatibility decision | Confirm or designate architecture authority | Supply product impact | Coordinate decision need | Recommend and supply technical evidence | Review process and authority; no technical approval |
| Implement authorized code, tests, and technical documentation | No routine involvement | No role authority | Coordinate scope and status | Execute | No role authority |
| Validate implementation and report technical results | May perform or accept author-observed evidence as project rules allow | Evaluate product acceptance intent | Track required evidence | Execute within authorization; report actual results | Review evidence rules; do not approve results |
| Governance review and corrective recommendation | Confirm any resulting rule or contract change | Supply product context | Supply delivery context | Supply technical context | Execute review and recommend |
| Change policies, roles, contracts, or project overrides | Confirm | Recommend within product responsibility | Recommend within delivery responsibility | Recommend technical corrections | Recommend governance corrections |
| Commit, push, tag, publish, use credentials, or modify remote systems | Separately authorize each applicable action | Separate authorization | Separate authorization | Separate authorization | Separate authorization |
| Specialist legal, security, privacy, financial, or platform-policy conclusion | Confirm disposition after qualified input | Identify product impact; do not impersonate specialist | Coordinate review need | Supply technical evidence; do not impersonate specialist | Identify missing boundary; do not impersonate specialist |

## Operating rules

1. Authorization attaches to a defined scope and action, not permanently to a role or conversation.
2. After a task or iteration is authorized, routine reversible work assigned as `Execute` does not require confirmation between each in-scope step.
3. A role marked `Recommend` or `Evidence` cannot convert its output into approval through documentation, silence, status changes, or implementation.
4. A material scope, product, architecture, specialist, remote, credential, or difficult-to-reverse boundary must follow the applicable confirmation or separate-authorization path.
5. Target-project rules may narrow or reassign these defaults when the override is explicit and properly routed. Higher-priority system and safety requirements always apply.

## Authoritative role definitions

- [Product Manager](product-manager.md)
- [Project Manager](project-manager.md)
- [Developer](developer.md)
- [Engineering Governance Reviewer](engineering-governance-reviewer.md)

The project author is included to make decision and escalation paths visible. The author is not an interchangeable agent role and retains the authority stated by the applicable target project.
