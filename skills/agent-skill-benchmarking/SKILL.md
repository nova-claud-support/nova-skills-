---
name: agent-skill-benchmarking
description: Design repeatable evaluations for SKILL.md instructions and AI-agent workflows. Use when comparing revisions, measuring task success, detecting regressions, or deciding whether a skill is ready to publish.
---

# Agent Skill Benchmarking

## Objective
Measure whether a skill reliably improves task outcomes across representative cases, rather than judging it by how polished its wording appears.

## Benchmark design
1. Define the skill's intended tasks, users, supported environments, and explicit non-goals.
2. Write a small task set covering common cases, edge cases, ambiguous requests, and near-miss cases where the skill should not activate.
3. Define expected outcomes before running evaluations. Include required artifacts, correctness checks, and prohibited behaviors.
4. Establish a baseline without the candidate skill, where practical.
5. Run the same cases with the skill under comparable model, tool, and context conditions.
6. Repeat variable cases enough to identify inconsistent behavior. Record model and environment versions.
7. Score outputs using a fixed rubric and preserve representative examples.
8. Compare results with the baseline and investigate regressions before release.

## Suggested scorecard
- Task completion: Was the requested outcome achieved?
- Correctness: Are facts, code, and decisions valid?
- Instruction adherence: Were constraints followed?
- Tool discipline: Were tools used only when appropriate?
- Robustness: Did edge cases receive safe, useful handling?
- Efficiency: Was unnecessary work avoided?
- Reproducibility: Can another evaluator repeat the test?

Use a documented scale such as 0–2 for each criterion: 0 = failed, 1 = partial, 2 = passed. Define criterion-specific evidence before scoring.

## Reporting
Include benchmark scope, test cases, environment, baseline, scores, failures, regressions, limitations, and a release recommendation. Preserve failed cases; do not silently remove inconvenient results.

## Release gates
- Every critical case passes.
- No new high-impact regression is unexplained.
- Scoring criteria are applied consistently.
- Limitations and untested areas are disclosed.

## Boundaries
Do not present a small benchmark as proof of universal reliability. Do not optimize only for a score; retain qualitative review for ambiguity, user experience, and safety.
