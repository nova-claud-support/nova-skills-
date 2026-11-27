---
name: skill-relevance-ranking
description: Rank discovered agent skills against a user's task using transparent relevance, quality, compatibility, safety, and maintenance criteria. Use when comparing multiple candidate skills or producing a recommended shortlist.
---

# Skill Relevance Ranking

## Objective
Select candidates that best satisfy the task rather than merely ranking by popularity.

## Evaluation dimensions
Score each dimension from 0 to 5 and record evidence:
- Task relevance: match to the requested outcome.
- Scope fit: focused enough to solve the task without unrelated behavior.
- Actionability: clear steps, inputs, outputs, and completion checks.
- Compatibility: fit with the user's model, host, tools, and platform.
- Safety: bounded permissions, safe handling of untrusted inputs, and no unjustified destructive behavior.
- Maintenance: meaningful versioning, recent validation, and issue handling where evidence exists.
- Documentation: understandable prerequisites, examples, and failure handling.

## Workflow
1. Convert the user's request into explicit evaluation criteria.
2. Exclude candidates with critical safety, licensing, or integrity problems.
3. Inspect candidate instructions and metadata.
4. Score each dimension independently; do not infer a score from popularity.
5. Apply task-specific weights and explain them.
6. Penalize missing prerequisites, unsupported platform assumptions, and unverified claims.
7. Group duplicates and near-duplicates before ranking.
8. Present the best-fit candidates with score breakdowns and concise trade-offs.
9. State when evidence is insufficient to rank confidently.
10. Re-evaluate if the user changes platform, constraints, or intended use.

## Default weighting
Task relevance 25%, safety 20%, compatibility 15%, actionability 15%, scope fit 10%, maintenance 10%, documentation 5%. Adjust only when the task clearly warrants it.

## Guardrails
- Safety and licensing failures are exclusion conditions, not weaknesses that popularity can offset.
- Do not fabricate stars, installs, update dates, or test results.
- Do not compare candidates using metrics from incompatible systems as if they were equivalent.
- Keep the scoring rationale visible and concise.

## Verification
- Every score has evidence.
- Exclusions are explained.
- Ranking reflects the user's constraints.
- Uncertainty and missing data are disclosed.
