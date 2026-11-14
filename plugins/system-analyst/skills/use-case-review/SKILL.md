---
name: use-case-review
description: Review use cases for consistent writing, terminology, structure, numbering, and business content across related use cases. Use when the user asks for a use-case review or advice on improving an existing draft.
---

# Review a use case

For repository work, follow the [shared architecture index workflow](../system-analyst/references/architecture-index.md). Locate the requested use case and related use cases that share an actor, business rule, state, or transition. Consult the project's glossary, template, and agreed requirements where available. If there are no comparable use cases, state that limit and review the target on its own merits.

- Compare spelling and domain terminology, actor and status names, titles, IDs and filenames, heading structure, step style, cross-references, and revision history. Use the documented convention or show representative examples when local practice varies.
- Walk the happy path, alternatives, and failures. Check that the actor and trigger are clear, branches refer to real steps, outcomes and state transitions agree with neighboring cases, and acceptance criteria cover the stated rules. Flag conflicting requirements and ask the user to resolve any business decision needed for a correction.
- Report each material finding with the affected use-case ID and location, comparison evidence when applicable, the consequence, and a concrete proposed correction. Lead with conflicting business behavior and missing outcomes. Apply requested use-case changes through [use-case-write](../use-case-write/SKILL.md), including the history update.
