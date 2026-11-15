---
name: clarify-business-decisions
description: Interview the user about an ambiguous or proposed business workflow using existing use cases, glossary terms, decisions, and code. Turn agreed rules into testable use-case changes.
---

# Clarify business decisions with project evidence

Start with the [shared architecture index workflow](../analyze-requirements/references/architecture-index.md). Identify the system, actor, goal, and decision in scope. Find the relevant use cases and any glossary entries or accepted decisions that constrain them. Check implementation and tests where current behavior matters. Record the use-case ID and step, term, decision reference, or code location behind each material conflict. Treat current behavior and documented intent as evidence the user can use to resolve a conflict.

## Interview in decision order

1. Ask the smallest set of independent questions that can be answered now. Resolve questions about the actor, scope, or state first when later rules depend on them. Use sources to resolve factual questions. Explain what each unresolved decision changes and offer a recommendation with its trade-off when supported.
2. Probe each proposed rule with a concrete alternative or failure case. For example, settle who may reopen a closed case before asking whether reopening restores its prior assignee. Ask what a user can observe and what state results.
3. Carry agreed answers into the next round. Challenge overloaded terms against the existing glossary and capture confirmed definitions. Surface which use-case steps, alternatives, and acceptance criteria each decision affects. Keep deferred decisions visible and say which outcomes still depend on them.

## Carry decisions into the documentation

Summarize confirmed rules, affected use-case IDs and steps, observable outcomes or acceptance criteria, and open decisions. For new use cases, identify the actor, goal, trigger, and proposed flow before handing off.

- Use [write-use-case](../write-use-case/SKILL.md) for requested new or revised use cases. Pass it the agreed decisions and their sources so it can reuse the answers, retain existing IDs, and update the revision history. Use [review-use-case](../review-use-case/SKILL.md) when the change affects related use cases. For a full comparison of specified and implemented behavior, use [verify-use-case-implementation](../verify-use-case-implementation/SKILL.md).
- Record confirmed terms in the project's canonical glossary when documentation updates are in scope. Keep business rules in the use cases. Flag a proposed architecture change and its affected decision separately. If an architecture decision record is requested, use the project's established workflow, including the `create-adr` skill from arc42 Architect when available.
- For a discussion, present proposed documentation changes in chat. When editing is requested, follow the project conventions and shared index for the affected artifacts. Resolve any remaining uncertainty about their locations before editing.
