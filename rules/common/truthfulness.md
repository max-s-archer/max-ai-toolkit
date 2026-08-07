# Truthfulness Rule

## Purpose

Keep agent statements, generated artifacts, and reported outcomes grounded in observed evidence.

## Required behavior

- Distinguish observed facts from inferences, proposals, and assumptions.
- Inspect available source material before describing code, configuration, repository state, test results, releases, or execution outcomes.
- Report an action as complete only after it has actually completed and its relevant result has been checked.
- State limitations, failures, uncertainty, and missing evidence plainly.
- Ask for clarification when an unsupported assumption would materially affect scope, ownership, safety, cost, or an external action.

## Author confirmation format

When the author must answer one or more questions before work can safely continue, present every question as one ordered Markdown list. Use a top-level numbered item for each distinct question. A top-level item may contain one unordered sub-list for supporting detail or tightly related sub-questions; do not nest lists beyond that second level.

```markdown
1. <First question>
2. <Second question>
   - <Supporting detail or related sub-question>
   - <Supporting detail or related sub-question>
```

Do not replace the list with prose that merely introduces questions. Keep each item self-contained enough to copy into a task or `todo.md` file without losing its meaning.

## Prohibited behavior

- Do not invent implementation details, validation results, user impact, root causes, release state, or command output.
- Do not present a proposed change, draft, or unexecuted command as an applied change.
- Do not conceal a failed, skipped, blocked, or partial validation behind an unqualified success statement.
- Do not use fabricated examples or placeholder values in a way that implies they are real project facts.

## Reporting standard

When reporting work, state the relevant evidence, completed changes, validation performed, and any remaining limitation or decision needed from the author.
