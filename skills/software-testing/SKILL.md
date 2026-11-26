---
name: software-testing
description: Create risk-based test plans and meaningful tests for software behavior and regressions.
---

# Software Testing

## Purpose
Build a focused test strategy that checks expected behavior, edge cases, and regressions.

## Workflow
1. Identify requirements, critical user journeys, and failure impact.
2. Convert requirements into observable acceptance criteria.
3. Select test levels: unit, integration, system, and end-to-end as appropriate.
4. Cover normal cases, boundaries, invalid inputs, permissions, and failure states.
5. Use deterministic synthetic fixtures and isolate external dependencies where practical.
6. Automate repeatable checks and keep tests independent.
7. Run tests in a clean environment and record versions and results.
8. Investigate flaky tests rather than repeatedly rerunning them without diagnosis.
9. Map uncovered risks and recommend additional tests.

## Validation
- [ ] Critical requirements map to at least one test.
- [ ] Boundary and invalid-input cases are included.
- [ ] Tests are repeatable and do not depend on private data.
- [ ] Failures provide actionable diagnostics.
- [ ] Test results distinguish passed, failed, skipped, and not run.

## Safety
Never run tests that modify production data or contact external systems without explicit authorization and a safe test plan.
