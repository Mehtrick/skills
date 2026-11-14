---
name: arc42-quality-scenarios
description: "Write measurable and prioritized arc42 section 10 quality scenarios from a concrete stimulus, system response, and response measure."
---


# Quality Scenarios

1. Read existing scenarios and the project's quality model. The [bundled reference](../arc42-quality-review/references/quality-model.md) can help if the project has none. Tie the scenario to a quality goal or architecture decision where possible.
2. Capture the source of the stimulus, conditions and workload, the relevant part of the system, its expected response, and a threshold with a unit and observation window where needed. Confirm any threshold that cannot be inferred from evidence.
3. Express the scenario in one cohesive sentence when it fits the project style. Example: “When 1,000 active users submit requests for ten minutes, the API completes at least 95% of requests within 250 ms.”
4. Preserve existing IDs and assign the next unused identifier, such as QS-8. Use local priorities. When A–D already applies, A is business-critical, B important, C desirable, and D optional.
5. If the task involves editing files, update the scenario table and chapter include or index as needed. Check that thresholds are testable and that the priority and quality subcharacteristic are supported.

Suggested columns: ID | Quality subcharacteristic | Priority | Scenario.
