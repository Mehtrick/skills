---
name: arc42-concept
description: "Create or revise arc42 section 8 crosscutting concepts and connect them to relevant architectural decisions."
---


# Crosscutting Concepts

For repository work, read `.agents/architecture.md` at the target repository root first. Follow the [project architecture index workflow](../arc42-architect/references/architecture-index.md) to verify relevant entries, find missing locations, and confirm uncertain paths before editing.

1. Locate the concept index, related concepts, and applicable ADRs. Establish which components or teams the concept affects and the crosscutting problem it addresses.
2. Describe context and problem, the proposed or adopted approach, constraints, and consequences. Identify rollout or adoption implications and trade-offs where relevant. Reference ADRs that directly govern the approach.
3. Follow local conventions. If the project uses numbered concept files, use the next unused ID in its sequence and a stable slug, for example CC-004-audit-logging. Use the [concept template](assets/concept.adoc) for AsciiDoc when appropriate.
4. Update the chapter index and validate links. Preserve IDs and anchors on revisions. Keep detailed topics in their existing subdirectories if the index already organizes them that way.
