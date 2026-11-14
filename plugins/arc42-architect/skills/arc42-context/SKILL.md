---
name: arc42-context
description: "Draft or review arc42 section 3, including the system boundary, business exchanges, technical interfaces, and their mapping."
---


# Context and Scope

Search the target repository for the relevant documents and conventions. If the source or destination is unclear after checking repository guidance and existing files, ask the user which location to use before editing.

1. Read the current system scope, introduction, constraints, and glossary. Set the system boundary and identify direct external actors and systems. Show indirect actors only where they explain a material exchange, and identify the intermediary.
2. For the business context, describe incoming and outgoing information in the domain language. Provide a context diagram and a table with Partner | Incoming information | Outgoing information where both clarify the boundary.
3. For the technical context, identify endpoints, channels, protocols, and directions with evidence. Provide a separate diagram and a table with Technical partner | Interface | Notes. If there are multiple technical realizations of a business exchange, show the mapping explicitly.
4. Keep internal decomposition in section 5. Check that partner names, directions, diagram edges, and tables agree. Mark unverified protocols and boundary decisions as open questions.

Use the project diagram format. In an AsciiDoc project with diagram tooling, PlantUML is suitable for the two views.
