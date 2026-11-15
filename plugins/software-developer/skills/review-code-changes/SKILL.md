---
name: review-code-changes
description: Review a diff, pull request, or working-tree change for fit with the project's development guidelines and architecture decisions, code quality, and security.
---

# Review Code Changes

## Establish scope and project rules

1. Identify the changes and comparison base from the request. For a pull request, use its diff or compare its head with the merge base of its target branch. For a review of current work, inspect staged, unstaged, and relevant untracked files. State the scope reviewed. Ask for clarification when plausible scopes would materially change the review.
2. Read the repository instructions that apply to each changed area, including directory-specific guidance. Search for development standards, lint and build configuration, and architecture documentation. Look for `architect.md`, including in hidden directories, and read it and its linked decisions when present. Other discovery points include an architecture index such as `.agents/architecture.md`, an arc42 decision section, or locations identified by the project's instructions. Check which architectural decisions apply to the changed components and whether later decisions supersede them.
3. Read comparable neighboring code, tests, and callers. Use explicit project rules and applicable architecture decisions as the review criteria. Where they leave room for judgment, use established patterns in the affected module. Surface conflicting guidance when it affects the assessment.

## Review the change

- **Project consistency.** Check whether the change belongs in its chosen module and follows the project's dependency direction and interface boundaries. Compare domain naming, API and error conventions, test structure, and reuse of existing components with comparable code. For a deviation, cite the applicable rule, architecture decision, or comparable implementation and explain the practical consequence.
- **Code quality and correctness.** Trace affected callers and observable behavior, including failure paths. Check for regressions, missing assertions for changed behavior, avoidable complexity, duplicate logic, and unused variables or imports. Run relevant project tests and static checks where feasible.
- **Security.** Trace changed data and privileges from entry points to sensitive operations. Check applicable authorization and isolation rules, validation of external input, handling of secrets and sensitive data, and the impact of dependency or configuration changes. Ground each finding in a concrete path and its possible impact.

## Report findings

Keep standalone reviews read-only. Lead with actionable findings ordered by severity. For each finding, cite the changed file and line, describe the failure or risk, and suggest a focused correction. Include the source of any violated rule or architectural decision. If there are no actionable findings, say so. List the checks run and any material gaps in verification.
