---
name: skill-improvement-cycle
description: Improve an agent skill through baseline evaluation, one-change experiments, regression checks, and evidence-based retention or rollback.
---

# Skill Improvement Cycle

## Purpose
Establish a controlled process for improving skill quality without introducing regressions or unverified claims.

## When to use
- Refining a skill that produces inconsistent results.
- Comparing alternative instruction structures.
- Maintaining a skill library through repeatable quality reviews.

## When not to use
- When there is no baseline example or acceptance criterion.
- When an improvement would expand the skill beyond its authorized scope.

## Requirements
- Current skill version.
- Representative, non-sensitive test tasks.
- Expected outcomes or a review rubric.
- A way to preserve the previous version.

## Workflow
1. Record the current version and its intended behavior.
2. Select representative tests covering normal, edge, and ambiguous cases.
3. Run or review the baseline and record observable failures.
4. Choose one improvement hypothesis at a time.
5. Change only the smallest relevant section.
6. Re-run the same tests and compare outcomes against the baseline.
7. Check for regressions in safety, scope, clarity, and output consistency.
8. Keep the change only when evidence shows a meaningful improvement.
9. Otherwise restore the previous version and document why.
10. Record the new version's behavior and remaining limitations.

## Experiment record
- Skill name and version
- Hypothesis
- Test cases
- Baseline observations
- Change made
- Post-change observations
- Regression findings
- Decision and rationale

## Validation
- [ ] A baseline exists.
- [ ] Tests are repeatable and use non-sensitive inputs.
- [ ] Each experiment changes one primary factor.
- [ ] Regression checks include safety and scope.
- [ ] Keep-or-rollback decisions cite observed results.
- [ ] Previous versions remain recoverable.

## Safety and privacy
Never use real credentials, private user records, or unauthorized targets as test data. Do not optimize a skill to bypass safety or access controls.