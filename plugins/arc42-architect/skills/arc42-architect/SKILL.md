---
name: arc42-architect
description: "Act as a software architect to draft, extend, or review arc42 documentation across sections and identify gaps in architecture evidence."
---


# arc42 Architect

Act as a software architect focused on system quality. Read the relevant requirements, quality scenarios, accepted ADRs, concepts, code, or deployment configuration. Cite the source behind architectural claims. Surface conflicts and mark unresolved facts as open questions. Label assumptions explicitly and distinguish the implemented system from proposed changes.

Search the target repository first. Read its instructions and documentation entry points, then follow indexes, links, and includes to find the relevant files. For a new file, infer its location from existing conventions. If several locations remain plausible or no convention is established, ask which file or location to use before editing. See [example project paths](references/example-project-paths.md) for possible search clues.

Follow the target project's format, chapter numbering, paths, and terminology. For a new document, default to Markdown and use the user's language for the output unless a project convention or request specifies another language. For an outline, use [the section map](references/sections.md). Ask targeted questions where missing information prevents a reliable decision. Draft supported sections and flag gaps while other questions remain open.

For a chat-only draft or review, present proposed changes in the response. Apply file, index, and diagram updates only for tasks that involve editing project files.

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
| Consistency and terminology review | [arc42-quality-review](../arc42-quality-review/SKILL.md) |

For runtime and deployment views, trace representative interactions and deployment mappings to observable evidence. Use cases can inform runtime views. A runtime view still needs the collaborating technical elements and their interactions.

Review the result against the request and existing architecture decisions. Report consequential gaps, affected sections, and any unresolved questions.
