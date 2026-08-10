# Cross-Platform Portability Rule

## Purpose

Keep shared project documentation, low-fidelity diagrams, paths, and command guidance practical to read, copy, edit, and execute across supported devices and terminals.

## Required behavior

- When creating or modifying shared project documentation, use portable Markdown and ASCII structural notation by default.
- Do not use decorative or input-method-specific symbols for document structure, including non-ASCII corner quotation marks, typographic quotation marks, typographic dashes, ellipses, arrows, or directory box-drawing glyphs.
- Use portable replacements such as double quotes, single quotes, `-`, `...`, `->`, indentation, and Markdown lists.
- Do not present a shell-specific command, path form, environment-variable syntax, or control operator as cross-platform.
- When a command is platform- or shell-specific, label its required operating system and shell. Provide a relevant alternative when one exists.

## Low-fidelity documentation

- Use a low-fidelity diagram when it materially improves understanding of layout, hierarchy, flow, or ownership.
- Build low-fidelity diagrams with spaces, `|`, and `-`. Use them to show structure, not final visual design.
- Represent directory structures with indented `-` lists. Do not use directory box-drawing glyphs.

```text
-----------------------
| Header              |
-----------------------
| Main content        |
|                     |
-----------------------
| Bottom navigation   |
-----------------------
```

```text
projects/
- registry.md
- <project-id>/
  - project.md
  - active/
```

## Exceptions

- Preserve characters required by source code, protocols, user-visible product text, quoted source material, or an explicitly documented product contract.
- This rule does not prohibit Chinese, English, or other natural-language prose. It governs structural and copyable technical notation.

## Verification

Before reporting shared documentation complete, verify that copyable paths, commands, and low-fidelity diagrams follow this rule and that every platform-specific instruction is clearly labeled.
