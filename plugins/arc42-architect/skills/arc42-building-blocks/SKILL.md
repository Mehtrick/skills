---
name: arc42-building-blocks
description: "Draft or review arc42 section 5, including system-level decomposition, component interfaces, and detailed building block documentation."
---


# Building Block View

1. Inspect the system-level whitebox, the affected building block, neighboring descriptions, and relevant code or configuration. Identify where the change belongs and infer the correct heading level from the parent include or document hierarchy.
2. Describe each block's responsibility, interfaces and directions, principal capabilities, relevant quality properties, code location, and linked decisions. Link traceable evidence. Add a diagram where it helps explain interfaces or dependencies. Keep its names and relationships aligned with the table.
3. For a new repository-specific block, reuse the existing naming and numbering. Where the project uses separate AsciiDoc files, [the building block template](assets/building-block.adoc) provides a starting point. Update the parent include or link in the appropriate place and check the rendered heading hierarchy.
4. Keep the overview and detail views consistent. Flag missing ownership, unclear interface directions, and unexplained dependencies.
