---
name: arc42-quality-tree
description: "Build or review an evidence-backed arc42 section 10 quality tree from quality goals, measurable scenarios, and accepted ADRs."
---


# Quality Tree

1. Read section 1 goals, accepted ADRs, and section 10 scenarios. Use the local quality model or the [bundled reference](../arc42-quality-review/references/quality-model.md) to map each piece of evidence to a subcharacteristic.
2. Include branches supported by a goal, scenario, or accepted ADR. Exclude draft, rejected, or superseded decisions as evidence of adopted architecture. Use the ADR's own status rather than inferring it from mentions in other documents.
3. Group branches by characteristic then subcharacteristic. Where priorities are represented, apply the highest supporting priority: architecture quality goal, then A through D. Leave an ADR-only node uncolored. Attach scenario IDs before ADR IDs under the relevant subcharacteristic.
4. Update the existing chapter or diagram location. In an AsciiDoc project using an inline PlantUML mind map, retain it inline and keep its legend beside it. See [diagram syntax and priority example](references/plantuml.md).
5. Check that every included ID exists and that links, priorities, and supporting evidence agree.
