---
name: arc42-constraints
description: "Draft or review arc42 section 2 for technical, organizational, and convention-based architecture constraints."
---


# Architecture Constraints

Search the target repository for the relevant documents and conventions. If the source or destination is unclear after checking repository guidance and existing files, ask the user which location to use before editing.

1. Read the current chapter, requirements, applicable policies, and glossary. Identify binding constraints and trace each to a source or an explicit user statement.
2. Group constraints into technical, organizational, and applicable conventions. Record the restriction, rationale or authority, affected scope, and architectural consequence. Distinguish externally imposed constraints from design choices whose rationale belongs in an ADR.
3. Test whether each restriction limits an architectural choice. Flag duplicates, conflicts, temporary constraints, and exceptions. Check local versus deployed environments separately when rules differ.
4. Edit the relevant section using existing tables and terms. For a new table use Constraint | Source or rationale | Architectural consequence. When multiple delivery targets create materially different constraints, a compact table mapping targets to restrictions can clarify the impact.
