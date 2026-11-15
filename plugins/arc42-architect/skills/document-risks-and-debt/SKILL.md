---
name: document-risks-and-debt
description: "Create or update arc42 section 11 architecture risks and technical debt, including impact, mitigation, and lifecycle status."
---

# Risks and Technical Debt

For repository work, follow the [project architecture index workflow](../document-architecture/references/architecture-index.md) to verify relevant entries, find missing locations, and confirm uncertain paths before editing.

1. Identify whether the entry concerns a possible future event or an existing compromise. Inspect current entries and keep the project's numbering, status labels, and display conventions.
2. For risk, capture the event and cause, likelihood, severity, priority rationale, mitigation, and contingency. For debt, capture the existing compromise, its observed effects, priority, and remediation. Record ownership or an estimate if available and flag missing facts.
3. Allocate a stable ID if needed, for example RISK-004 or DEBT-008. Use the [risk template](assets/risk.adoc) or [debt template](assets/debt.adoc) for AsciiDoc when appropriate.
4. Update the section overview, status, and references. On status changes retain the rationale or mitigation history. Verify that the overview and detail entry agree.
