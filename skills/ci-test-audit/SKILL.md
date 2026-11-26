---
name: ci-test-audit
description: Audit CI pipelines and automated tests for missing coverage, false passes, stale fixtures, flaky behavior, unsafe skips, and unnecessary runtime cost.
---

# CI and Test Audit

## Mission
Determine whether automated checks detect the regressions they claim to detect. Improve reliability and efficiency without weakening meaningful coverage.

## Required context
- Repository instructions and test commands.
- Current revision and working-tree state.
- CI workflow definitions and job dependencies.
- Test framework, runtime, and supported environments.
- User authorization for edits to tests or pipeline configuration.

Investigation does not automatically authorize changing workflows, opening issues, pushing, or merging.

## Workflow

### 1. Map the executed pipeline
1. Trace workflow triggers, path filters, job dependencies, reusable workflows, and required status checks.
2. Identify the exact scripts and commands each job runs.
3. Follow test discovery, fixture generation, report creation, and result gates.
4. Distinguish required checks from optional jobs and documented prerequisite skips.
5. Record the revision and environment associated with every result.

Do not assume a test runs because a file exists or a workflow has a descriptive name.

### 2. Find weak or missing protection
Inspect for:
- required tests that are not discovered;
- missing reports that still allow a green result;
- stale fixtures that no longer match production contracts;
- mocks that reproduce the implementation instead of validating it;
- assertions that cannot fail for the regression they describe;
- swallowed subprocess failures or ignored exit codes;
- blanket retries, broad skips, and excessive timeouts;
- platform-specific paths that silently omit required coverage;
- concurrency, cancellation, permission, and cleanup cases that are untested.

### 3. Prove suspicious behavior safely
For each finding, define the expected behavior and the test that should detect a regression. Use a minimal local reproduction or an isolated fixture.

When evaluating whether an assertion is meaningful, use a controlled test mutation in an isolated copy. Restore the original state and verify the working tree afterwards. Never mutate production systems or shared CI environments to test a hypothesis.

### 4. Assess efficiency
Use existing CI timing and failure artifacts first. Measure equivalent runs before claiming a speed improvement.

Prefer:
- eliminating proven duplicate setup;
- reusing immutable build artifacts with correct cache keys;
- narrowing test selection only when all affected paths remain covered;
- reducing redundant subprocess startup;
- improving failure diagnostics.

Do not remove distinct assertions, skip slow tests indiscriminately, or reuse stale passes as evidence for a current environment.

### 5. Fix and verify
When changes are authorized:
1. Make the smallest correction at the owning workflow, script, fixture, or test boundary.
2. Add a regression test that fails on the original behavior.
3. Run focused tests and all affected test-discovery paths.
4. Validate failure behavior as well as the passing path.
5. Review current CI results for the exact tested revision.
6. Inspect the complete diff for weakened gates or unrelated edits.

## Finding format
For every finding report:
- Severity and affected workflow.
- Exact revision and command.
- Expected versus observed behavior.
- Reproduction evidence.
- User or maintainer consequence.
- Recommended correction.
- Validation and remaining uncertainty.

Classify each item as a reproduced defect, confirmed coverage gap, supported cost, hypothesis, or unavailable evidence.

## Safety and scope
Do not hide failures, weaken authorization checks, expose secrets in logs, or run destructive tests against shared infrastructure. Keep raw logs and sensitive artifacts private. Never claim CI is healthy based only on a local subset.
