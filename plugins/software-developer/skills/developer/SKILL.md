---
name: developer
description: Implement a use case or directly supplied requirement with test-driven development, domain terminology, and a final review of code quality and requirement coverage.
---

# Developer

## Find the requirements

1. Read the target repository's instructions. Find the relevant documentation, implementation entry points, nearby tests, and test commands. Consult the project glossary and applicable architecture decisions when available.
2. Prefer applicable use cases written by the analyst. Look for the project's analyst notes and use-case index through its instructions, documentation, and file search, including hidden directories. `analyst.md` and `.agents/architecture.md` are examples of discovery points. Verify the links against the actual use-case documents and match the use case to the requested behavior by ID, goal, or scope. Use directly supplied requirements when no applicable use case is available or the user specifies them as the source. If an explicitly requested use case remains missing or ambiguous, or the sources disagree on behavior, ask a focused question before editing the affected behavior.
3. Identify the observable outcomes in scope. For a use case, keep its ID and step or criterion references so each system response and business rule can be traced to a test. Include the main flow, alternatives, failures, preconditions that affect behavior, and postconditions. Translate actor actions into test setup or inputs and assert the resulting system behavior. Apply the same coverage check to explicitly supplied requirements.

## Implement with TDD

1. Choose one behavior and write its test before changing production code. Exercise the behavior through the project's normal entry point using its existing test conventions. Name the test in the domain language and derive its expectations from the requirement.
2. Run the focused test. Proceed to implementation only after the test runs and fails because the intended behavior is missing or wrong. Resolve discovery, build, fixture, and environment failures first. If the test passes, check that it exercises the intended case. When the behavior is already present, record that coverage and move to the next behavior.
3. Implement the smallest change that makes the test pass and run it again. Use Clean Code, KISS, and SOLID to keep responsibilities focused and interfaces small. Reuse established code and introduce abstractions when the behavior warrants them. Use the use-case and glossary terms in production names and test names, adapted to the project's naming conventions. For example, a step called “Cancel order” should be recognizable in a `cancelOrder` operation and in a test describing when an order can be cancelled.
4. Repeat for the remaining behaviors. Refactor as needed with tests green and rerun the affected tests after each refactor. Run the project's relevant regression suite and resolve failures caused by the change.

## Review before handing off

1. After the tests pass, follow [Review Code Changes](../review-code-changes/SKILL.md) on the implementation and test diff. Resolve actionable findings within scope. Use another red–green cycle for fixes that change behavior.
2. Walk the requirements or use case again. For each in-scope step and rule, identify the test and the assertion that verifies it. Check the actual outcomes for success, alternatives, and failures. Address coverage gaps through another red–green cycle and rerun the tests and checks after review fixes.
3. Report the commands and results that demonstrated red and green, the final checks, and the requirement or use-case references with their corresponding tests. Identify any remaining coverage gaps or checks you could not run.
