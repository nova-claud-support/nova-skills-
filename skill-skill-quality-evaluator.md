---
name: skill-quality-evaluator
description: Evaluate agent skill files for clarity, scope, actionability, correctness, safety, maintainability, and testability before acceptance.
---

# Skill Quality Evaluator

## Purpose
Review a skill specification and produce evidence-based findings with clear acceptance criteria.

## When to use
- Reviewing a new SKILL.md before adding it to a library.
- Auditing existing skills for duplication, ambiguity, or missing validation.
- Preparing a focused improvement plan for an underperforming skill.

## When not to use
- When the task requires executing the skill's full workflow rather than reviewing its specification.
- When required files are unavailable; request the missing material instead of guessing.

## Requirements
- The complete skill file.
- Any referenced local assets or scripts that are claimed to be required.
- The intended agent environment, if environment-specific behavior matters.

## Evaluation dimensions
1. Identity: valid metadata, stable name, concise description.
2. Scope: clear use cases, exclusions, and expected outputs.
3. Actionability: ordered steps with concrete decisions and operations.
4. Correctness: commands, APIs, and claims are plausible and verifiable.
5. Validation: observable completion checks and failure handling.
6. Safety: authorization boundaries, privacy, and secret handling.
7. Maintainability: low duplication, modular structure, and clear terminology.
8. Portability: explicit assumptions and minimal unnecessary dependencies.

## Workflow
1. Parse metadata and verify naming consistency.
2. Summarize the skill's intended outcome in one sentence.
3. Identify vague instructions and convert them into testable requirements.
4. Check whether every claimed dependency is present or explicitly optional.
5. Look for contradictory instructions, unsupported claims, and unsafe defaults.
6. Compare the skill's scope with neighboring skills to identify overlap.
7. Assign findings by severity: critical, major, minor, or suggestion.
8. Provide specific edits and a final decision: accept, revise, or reject.

## Output format
- Verdict
- Scope summary
- Findings grouped by severity
- Missing requirements
- Suggested changes
- Validation checklist

## Validation
- [ ] Every finding points to a concrete passage or omission.
- [ ] Severity reflects practical impact.
- [ ] Recommendations are specific and actionable.
- [ ] No unsupported claim is presented as verified.
- [ ] The verdict follows from the findings.

## Safety and privacy
Do not reproduce credentials or sensitive content found during review. Report their presence and recommend secure handling without exposing the values.