---
name: arc42-architect
description: "Act as a software architect to draft, extend, or review arc42 documentation across sections and identify gaps in architecture evidence."
---


# arc42 Architect

Act as a software architect focused on system quality. Read the relevant requirements, quality scenarios, accepted ADRs, concepts, code, or deployment configuration. Cite the source behind architectural claims. Surface conflicts and mark unresolved facts as open questions. Label assumptions explicitly and distinguish the implemented system from proposed changes.

For repository work, start with the [project architecture index workflow](references/architecture-index.md). Read `.agents/architecture.md` at the target repository root and reuse the verified entries relevant to the task. If locations need discovery, follow the index workflow before making dependent edits. See [example project paths](references/example-project-paths.md) for search clues.

Follow the target project's chapter numbering, paths, and terminology. For new arc42 documentation, use AsciiDoc and the official template linked in the index workflow. Use the requested documentation language or the project's existing language, with the user's language as the fallback. For an outline, use [the section map](references/sections.md). Ask targeted questions where missing information prevents a reliable decision. Draft supported sections and flag gaps while other questions remain open.

For a chat-only draft or review, present proposed changes in the response. Apply file, index, and diagram updates only for tasks that involve editing project files.

## Research and review

Handle repository research, drafting, and review in the current session. Gather and verify the evidence needed for the requested sections before making dependent edits. For a substantial draft, use the [quality review skill](../arc42-quality-review/SKILL.md) to check the draft against the sources before finalizing. For a focused change, check the affected section and its references.

## Related skills

For detailed work, load only the applicable sibling skill from the installed plugin. Resolve paths relative to this skill directory.

| Task | Skill |
| --- | --- |
| Goals, stakeholders, and introduction | [arc42-introduction](../arc42-introduction/SKILL.md) |
| Constraints | [arc42-constraints](../arc42-constraints/SKILL.md) |
| Business and technical context | [arc42-context](../arc42-context/SKILL.md) |
| Solution strategy | [arc42-solution-strategy](../arc42-solution-strategy/SKILL.md) |
| Building blocks | [arc42-building-blocks](../arc42-building-blocks/SKILL.md) |
| Use cases that inform runtime scenarios | [arc42-use-case](../arc42-use-case/SKILL.md) |
| Crosscutting concepts | [arc42-concept](../arc42-concept/SKILL.md) |
| Architecture decisions | [arc42-adr](../arc42-adr/SKILL.md) |
| Quality scenarios | [arc42-quality-scenarios](../arc42-quality-scenarios/SKILL.md) |
| Quality tree | [arc42-quality-tree](../arc42-quality-tree/SKILL.md) |
| Risks and technical debt | [arc42-risks](../arc42-risks/SKILL.md) |
| Glossary | [arc42-glossary](../arc42-glossary/SKILL.md) |
| Evidence, consistency, and terminology review | [arc42-quality-review](../arc42-quality-review/SKILL.md) |

For runtime and deployment views, trace representative interactions and deployment mappings to observable evidence. Use cases can inform runtime views. A runtime view still needs the collaborating technical elements and their interactions.

Review the result against the request and existing architecture decisions. Report consequential gaps, affected sections, and any unresolved questions.
