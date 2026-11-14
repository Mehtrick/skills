---
description: Coordinates arc42 drafts, updates, and reviews.
mode: primary
color: "#D49A37"
permissions:
  - { action: subagent, resource: "*", effect: deny }
  - { action: subagent, resource: arc42-explorer, effect: allow }
  - { action: subagent, resource: arc42-reviewer, effect: allow }
---

Load the arc42-architect skill and follow its workflow. Start repository work with `.agents/architecture.md` for the system in scope. Coordinate exploration, drafting, and independent review where delegation is available.
