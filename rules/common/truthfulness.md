# Truthfulness Rule

## Purpose

Keep agent statements, generated artifacts, and reported outcomes grounded in observed evidence.

## Required behavior

- Distinguish observed facts from inferences, proposals, and assumptions.
- Inspect available source material before describing code, configuration, repository state, test results, releases, or execution outcomes.
- Report an action as complete only after it has actually completed and its relevant result has been checked.
- State limitations, failures, uncertainty, and missing evidence plainly.
- Ask for clarification when an unsupported assumption would materially affect scope, ownership, safety, cost, or an external action.

## Author confirmation block

When author confirmation is required before work can safely continue, use the [Author Confirmation Template](../../templates/author-confirmation-template.md). Use this block when a missing fact, decision, or authorization would materially affect scope, ownership, safety, cost, an external action, or irreversible work.

Place only necessary factual background before a `## Author Confirmation Required` heading. Do not mix background into the numbered questions. Under that heading, present every independent question as one item in a single ordered Markdown list. Each item must include a bold **Question:** label, a bold **Why it matters:** label, and a bold **Answer:** label with a clear response location. Include **Recommended default:** only when a reasonable default exists; it never constitutes approval.

```markdown
<Brief factual background, if needed.>

## Author Confirmation Required

1. **Question:** <Decision or missing fact to confirm>
   - **Why it matters:** <Why safe progress depends on this answer>
   - **Recommended default:** <Optional reasonable default>
   - **Answer:**
```

Use one top-level item for each distinct decision. A top-level item may contain one unordered sub-list for the required labels, supporting detail, or tightly related choices; do not nest lists beyond that second level. Keep every question self-contained enough to copy into a task or `todo.md` file without losing meaning. Do not replace the block with prose that merely introduces questions, and do not treat an empty answer or an unchallenged default as authorization.

## Prohibited behavior

- Do not invent implementation details, validation results, user impact, root causes, release state, or command output.
- Do not present a proposed change, draft, or unexecuted command as an applied change.
- Do not conceal a failed, skipped, blocked, or partial validation behind an unqualified success statement.
- Do not use fabricated examples or placeholder values in a way that implies they are real project facts.

## Reporting standard

When reporting work, state the relevant evidence, completed changes, validation performed, and any remaining limitation or decision needed from the author.
