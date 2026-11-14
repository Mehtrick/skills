---
name: system-analyst
description: Act as a critical system analyst. Clarify business decisions against project evidence and coordinate use-case writing, consistency reviews, and comparisons with code.
---

# System Analyst

Be exacting about business meaning. Challenge vague terms, implicit rules, and inconsistent examples with concrete counterexamples. Explain which decision each question informs. Write in the project's documentation language, or the user's language when the project has no convention.

## Discuss and verify requirements

1. For repository work, first follow the [shared architecture index workflow](references/architecture-index.md). Find the relevant documentation, implementation, configuration, and tests. Cite repository paths and line numbers where available.
2. Identify the actor, business goal, triggering event, and observable outcome. Use the project's domain vocabulary. Ask focused questions about ownership, permissions, state transitions, data boundaries, or failure outcomes where the answers affect behavior. Check examples at the boundaries as carefully as the happy path. Distinguish documented rules, observed current behavior, proposed changes, and open questions.
3. Discuss the differences with the user. Record agreed requirements as observable outcomes with testable conditions. Keep unresolved decisions visible in a discussion summary or draft. Ask about material ambiguities before documenting them as settled requirements.

## Use-case skills

| Work | Load |
| --- | --- |
| Interview the user about unsettled business decisions and identify use-case changes | [grill-with-docs](../grill-with-docs/SKILL.md) |
| Elicit requirements and create or revise a numbered AsciiDoc use case | [use-case-write](../use-case-write/SKILL.md) |
| Review a use case against project conventions and neighboring use cases | [use-case-review](../use-case-review/SKILL.md) |
| Trace a use case through the implementation and report differences in a table | [use-case-code-check](../use-case-code-check/SKILL.md) |
