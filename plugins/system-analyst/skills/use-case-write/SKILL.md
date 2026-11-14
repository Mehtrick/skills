---
name: use-case-write
description: Elicit and clarify business requirements, then write or revise a sequentially numbered textual AsciiDoc use case with a revision history. Use when the user asks to draft, create, or update a use case.
---

# Write a use case

For repository work, follow the [shared architecture index workflow](../system-analyst/references/architecture-index.md). Use the project's documentation language, with the user's language as the fallback.

## Clarify the requirements

Establish the actor and goal, trigger, preconditions, business rules, main outcome, and meaningful alternatives. Check applicable project documentation, code, and tests. Ask focused questions about missing or contradictory requirements that affect the flow or acceptance criteria. Relate each question to a concrete example or decision. Use answers already given. Wait for the answers to material questions before writing the use case. Distinguish intended changes from behavior already implemented.

## Agree on the destination and numbering

1. Look for existing use cases, templates, naming rules, numbering registers, and documentation indexes or AsciiDoc includes before asking. Look in the arc42 runtime view if the project uses arc42. If there is no established location, propose a suitable folder under the runtime view or the project documentation directory, for example `docs/`.
2. Before the first write, present the candidate and ask the user once which directory to use. Reuse the confirmed choice recorded in the shared architecture index or already provided by the user. Infer the filename pattern and numbering scope from the project's examples or conventions. When the pattern is unclear, ask and offer a numbered example such as `UC-001-cancel-order.adoc`. Combine the location and naming questions when both decisions are needed. Record confirmed conventions in the shared index.
3. Create one `.adoc` file per use case. Check the applicable register and existing files, then use the next unused sequential ID. Start at 1 if the sequence is empty and the project defines no other starting number. Recheck the ID and destination before writing. Put the ID in the document and follow the agreed filename pattern. Preserve existing IDs during revisions.

## Write and verify the document

- Use the bundled [AsciiDoc template](assets/use-case.adoc) and adapt headings to the project's conventions. Put the history table immediately after the title and any required header attributes. Use four columns in this order: Date, Version, Change, Name (`Datum`, `Version`, `Änderung`, `Name` in German). Add an entry for each revision, preserve prior entries, and sort newest date first. Follow project date and version conventions. For a fresh history without a project convention, use `YYYY-MM-DD` and integer versions starting at 1. Use the known editor name for attribution and ask if it cannot be established.
- Describe the flow in text. State the actor, goal, trigger, and preconditions. Number the main steps and describe observable actor actions and system responses. Tie alternatives and failures to the affected step, give the branch's return point or outcome, and state the resulting state. Derive testable acceptance criteria from the agreed rules.
- Check the flow and history against the agreed requirements and compare relevant conventions with neighboring use cases. Update any documentation index or include required by the project and verify its path.
