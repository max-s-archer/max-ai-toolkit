# Language Policy

## Purpose

Keep `max-ai-toolkit` efficient for Max's day-to-day work while ensuring that public-facing content and generated artifacts are accessible in English.

This policy is the authoritative source for language requirements. It applies to Toolkit content and to artifacts generated under Toolkit guidance unless a consuming project defines a stricter, explicitly scoped requirement.

## Default language

- Use English for public repository entry points, public documentation, reusable templates, examples intended for external readers, and all generated external artifacts.
- Use English for commit messages, annotated tag messages, release notes, pull-request text, issue text, and other repository-facing output.
- Chinese may be used for authoring instructions, private prompts, working notes, and Max-specific internal guidance when it improves maintenance.
- Preserve technical identifiers in their native form. Do not translate code, commands, paths, API names, product names, or standard protocol terms merely to satisfy this policy.

## File naming and bilingual content

- Use an English file without a language suffix as the public default: `architecture.md`.
- Use `.zh-CN.md` for a Chinese counterpart: `architecture.zh-CN.md`.
- Maintain a bilingual pair only when the content has sustained public or cross-project value. Do not create translations solely for structural symmetry.
- Treat each pair as one document in two languages. Keep their scope, requirements, examples, and normative meaning aligned.
- Identify one semantic source near the beginning of a bilingual document pair. Update that source first, then update its counterpart in the same change whenever practical. If synchronization must be deferred, state the discrepancy and its owner explicitly.

## External-output check

Before publishing or generating user-visible output, verify that:

1. The prose is English unless the intended audience is explicitly internal.
2. Templates and examples do not introduce Chinese into public artifacts.
3. Translated content does not change requirements or omit constraints from its semantic source.
4. Any project-specific language override is explicit, local to that project, and does not modify this Toolkit policy.
