---
name: analyze-requirements
description: Analyze business requirements against project documentation, code, and tests. Coordinate use-case writing, consistency reviews, and comparisons with code.
---

# Analyze Requirements

Be exacting about business meaning. Challenge vague terms, implicit rules, and inconsistent examples with concrete counterexamples. Explain which decision each question informs. Write in the project's documentation language, or the user's language when the project has no convention.

## Discuss and verify requirements

1. For repository work, first follow the [shared architecture index workflow](references/architecture-index.md). Find the relevant documentation, implementation, configuration, and tests. Cite repository paths and line numbers where available.
2. Identify the actor, business goal, triggering event, and observable outcome. Use the project's domain vocabulary. Ask focused questions about ownership, permissions, state transitions, data boundaries, or failure outcomes where the answers affect behavior. Check examples at the boundaries as carefully as the happy path. Distinguish documented rules, observed current behavior, proposed changes, and open questions.
3. Discuss the differences with the user. Record agreed requirements as observable outcomes with testable conditions. Keep unresolved decisions visible in a discussion summary or draft. Ask about material ambiguities before documenting them as settled requirements.

## Use-case skills

| Work | Load |
| --- | --- |
| Ask focused follow-up questions to clarify a business requirement | [ask-questions](../ask-questions/SKILL.md) |
| Interview the user about unsettled business decisions and identify use-case changes | [clarify-business-decisions](../clarify-business-decisions/SKILL.md) |
| Elicit requirements and create or revise a numbered AsciiDoc use case | [write-use-case](../write-use-case/SKILL.md) |
| Review a use case against project conventions and neighboring use cases | [review-use-case](../review-use-case/SKILL.md) |
| Trace a use case through the implementation and report differences in a table | [verify-use-case-implementation](../verify-use-case-implementation/SKILL.md) |
