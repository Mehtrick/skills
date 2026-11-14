---
name: use-case-code-check
description: Trace a use case through the existing code and tests, and report differences between specified and implemented behavior in a table. Use to compare implementation with a use case or check coverage of its flows and business rules.
---

# Compare a use case with code

For repository work, follow the [shared architecture index workflow](../system-analyst/references/architecture-index.md). Locate the use case and implementation entry points. Trace its numbered steps, rules, alternatives, and failure outcomes through the relevant code, configuration, and tests. Cite the path and line or symbol for each claim. Include implemented business behavior missing from the use case when it affects the observed outcome. Label paths you could not verify and explain the missing evidence.

Always report the comparison in a table. Use one row per material difference or evidence gap, with the relevant use-case ID and step. If the inspected behavior matches throughout, include a row stating the verified scope and that no differences were found there.

| Use case and step | Specified behavior | Implemented behavior and evidence | Status | Impact and proposed change |
| --- | --- | --- | --- | --- |
| `<ID>, main step 3` | `<Required outcome>` | `<Observed outcome with source reference>` | `<Match, mismatch, missing in code, missing in use case, or unverified>` | `<Business consequence and proposed change>` |

Distinguish a defect, stale documentation, and an intentional future requirement when the agreed business rule establishes which behavior is authoritative. Ask the user to resolve disputed rules before recommending which artifact to change. Apply requested use-case corrections through [use-case-write](../use-case-write/SKILL.md). Apply requested code corrections following the project's implementation and verification conventions.
