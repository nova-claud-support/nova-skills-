---
name: runtime-compatibility-testing
description: Test whether a skill behaves consistently across models and agent hosts, separating instruction portability from native loading and tool execution. Use before publishing a multi-model package or changing compatibility claims.
---

# Runtime Compatibility Testing

## Objective
Evaluate a skill with repeatable tests across different model and host combinations.

## Test dimensions
1. Parsing: frontmatter and Markdown are accepted.
2. Discovery: the host finds the skill automatically, when claimed.
3. Activation: relevant requests trigger it and irrelevant requests do not.
4. Instruction fidelity: required steps and constraints are followed.
5. Tool adaptation: unavailable tools trigger documented fallbacks.
6. Safety: permissions, privacy, and approval gates remain effective.
7. Output quality: deliverables meet acceptance criteria.
8. Resilience: ambiguous inputs and tool failures are handled honestly.

## Workflow
1. Select representative model families and host runtimes.
2. Record model version, host version, installation method, and enabled tools.
3. Create fixed normal, edge, ambiguous, and adversarial test cases.
4. Test manual-context loading separately from native discovery.
5. Run equivalent tasks with equivalent inputs and permissions.
6. Score each dimension pass, partial, or fail with evidence.
7. Record runtime differences without making the portable core vendor-specific.
8. Fix failures and rerun the full suite.
9. Publish a compatibility matrix with test date and limitations.

## Result matrix
| Model | Host | Load method | Tools | Instruction pass | Safety pass | Notes |
|---|---|---|---|---|---|---|

## Guardrails
- Do not claim support for an untested model or host.
- Do not compare models with unequal prompts, tools, or permissions.
- Native discovery failure does not prove Markdown instructions are unusable.
- Do not hide partial or failed results.

## Verification
- Tests are reproducible and conditions are equivalent.
- Model, host, and tool versions are recorded.
- Portability and native loading are reported separately.
- Compatibility statements match observed evidence.
