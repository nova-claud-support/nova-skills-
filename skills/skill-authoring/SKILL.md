---
name: skill-authoring
description: Create, structure, review, and maintain clear, testable agent skills using the NOVA SKILLS quality standard.
---

# Skill Authoring

## Purpose
Create or revise an agent skill that is focused, actionable, maintainable, and verifiable.

## When to use
- Creating a new SKILL.md.
- Turning a repeatable workflow into reusable agent instructions.
- Reviewing a skill for clarity, safety, and correctness.

## Requirements
- Identify the intended agent or tool environment.
- Define the task and boundaries.
- Verify commands, APIs, and dependencies before documenting them.
- Use synthetic examples; never include real credentials or private data.

## Workflow
1. Define the outcome in one sentence.
2. Describe requests that should trigger the skill.
3. State out-of-scope tasks and safety boundaries.
4. List tools, versions, permissions, and inputs.
5. Write concrete ordered steps and decision points.
6. Add representative examples and expected outputs.
7. Define checks that determine correctness.
8. Remove repetition, stale instructions, and unsupported claims.
9. Preserve required licensing notices and attribution.
10. Save the skill in a directory matching its frontmatter name.

## Validation
- [ ] Directory name matches frontmatter name.
- [ ] Description explains capability and activation context.
- [ ] Instructions are actionable and unambiguous.
- [ ] Requirements and permissions are explicit.
- [ ] Examples use synthetic data.
- [ ] Validation steps are included.
- [ ] Security, privacy, and licensing are addressed.

## Safety
Do not author instructions for unauthorized access, credential theft, malware deployment, destructive actions against third-party systems, or evasion of security controls. Cybersecurity skills must focus on defense and authorized lab environments.

## Maintenance
Review the skill when its target tools, APIs, or supported versions change. Update examples and validation steps together.