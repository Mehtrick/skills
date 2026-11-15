---
name: diagnose-bug
description: Investigate a reported bug, explain the likely cause with source locations and applicable use-case evidence, and reproduce it with an automated regression test before fixing it.
---

# Diagnose Bug

## Trace the symptom and report the likely cause

1. Collect the reported symptom, trigger, relevant inputs, and available logs or runtime details. Use the **Find the requirements** section of [Implement Feature](../implement-feature/SKILL.md) to find project guidance, related use cases, and nearby tests. Compare the observed behavior with the applicable use-case step or rule when a specification exists. Otherwise, establish the expected outcome from the report and the project's documented behavior. Ask a focused question if the expected outcome remains ambiguous.
2. Trace the affected path from the normal entry point to the observed result. Inspect relevant input handling, business rules and state changes, persistence, dependencies, and configuration. Use existing tests and error paths as evidence. Follow plausible alternative causes when the evidence supports them.
3. Before writing or running the reproduction test, tell the user what was observed, what should happen, and which condition most likely triggers the bug. List the relevant file paths and line numbers and explain what each shows. Cite the use-case ID and step or rule when available. Label the likely cause as a hypothesis and name any material uncertainty. Continue with the reproduction when the expected behavior is clear.

## Reproduce with an automated test

1. Reuse an automated test that exercises the trigger and asserts the expected outcome. Extend a nearby test or add a focused regression test if coverage is missing. Follow the project's runner, test names, fixtures, helpers, and setup. Exercise the business inputs through the established entry point and assert the expected observable output, error, or state. Keep the setup minimal while retaining the conditions that trigger the bug.
2. Run the test against the current production code and verify that it fails with the reported symptom. Record the command, expected result, and actual result. If the test passes or fails for another reason, revisit the trigger, inputs, and environment. If you still cannot reproduce the symptom, report what you tried and what evidence would help reproduce it.

## Fix and verify

Begin production changes only after an automated test reproduces the reported failure and the request includes a fix. Resume [Implement Feature](../implement-feature/SKILL.md) at the minimal implementation step. Rerun the regression test, then follow the review and verification steps. Report the confirmed cause, the code locations, and the test result before and after the fix.
