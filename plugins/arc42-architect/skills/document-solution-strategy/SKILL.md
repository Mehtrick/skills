---
name: document-solution-strategy
description: "Draft or review arc42 section 4, relating architecture principles, technology choices, and organization to system quality goals."
---

# Solution Strategy

For repository work, follow the [project architecture index workflow](../document-architecture/references/architecture-index.md) to verify relevant entries, find missing locations, and confirm uncertain paths before editing.

1. Read sections 1–3 and relevant ADRs before drafting. Extract the actual goals, constraints, and external dependencies that shape the solution.
2. Summarize the architecture principles with their system-level implications. Record core technologies with their roles and rationale. Include organizational decisions where responsibilities or team boundaries shape the architecture.
3. For each significant quality goal, describe the approach used to achieve it and identify the relevant trade-off or limitation. Trace to scenarios, concepts, or ADRs where available. Use the project's quality model, with the [bundled reference](../review-architecture/references/quality-model.md) as an optional aid.
4. Distinguish existing decisions from proposals. Check the strategy against constraints and avoid repeating detailed design already owned by a building block, concept, or ADR.

Suggested columns for a quality-driven strategy: Quality goal | Architectural approach | Evidence or decision.
