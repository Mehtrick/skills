---
name: arc42-adr
description: "Draft or revise an architecture decision record for arc42 section 9 with rationale, alternatives, quality impacts, and traceability."
---


# Architecture Decision Records

For repository work, read `.agents/architecture.md` at the target repository root first. Follow the [project architecture index workflow](../arc42-architect/references/architecture-index.md) to verify relevant entries, find missing locations, and confirm uncertain paths before editing.

1. Check that the choice has architectural consequences, such as effects across components, long-lived constraints, or measurable effects on system qualities. Read existing ADRs for numbering, status semantics, and language.
2. Gather the decision, context, deciding owner, date, considered alternatives, and consequences. Use a proposed status for a draft unless an accepted status has evidence. Mark missing owner, approval, or alternatives as open.
3. Describe why the option was selected and why viable alternatives were set aside. Record favorable and unfavorable effects. Identify a small number of material quality impacts with a short rationale, using the project's terminology or the [bundled quality model reference](../arc42-quality-review/references/quality-model.md).
4. For a new ADR, allocate the next unused ID and follow the local filename convention. Use the [ADR template](assets/adr.adoc) in an AsciiDoc project when appropriate. Update the chapter index or include list and check links and anchors. Link any superseded decisions without rewriting decision history.
