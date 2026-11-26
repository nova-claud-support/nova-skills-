---
name: skill-installation-planning
description: Prepare a safe, host-aware installation plan for an approved agent skill without assuming a universal folder layout or automatically executing unreviewed code. Use after a user selects a candidate and asks how to add it to an agent environment.
---

# Skill Installation Planning

## Objective
Translate an approved skill into a reversible installation plan for the user's actual host environment.

## Workflow
1. Confirm the selected skill, target host, project or user scope, and requested installation method.
2. Verify the skill's contents, license, prerequisites, and compatibility before preparing installation.
3. Determine the host's documented skill discovery mechanism and expected directory structure.
4. Distinguish native automatic loading from manually supplying the skill as context.
5. Identify all files to be copied and any scripts or dependencies; do not execute them as part of planning.
6. Check for existing files and name collisions before proposing changes.
7. Prefer project-local installation when the skill is needed only for one project.
8. Prepare a reversible plan with backup or restore steps.
9. Request explicit approval before writing files, changing configuration, or installing dependencies.
10. After an authorized installation, verify file placement and whether the host actually discovers the skill.
11. Report limitations if the host does not support automatic loading.

## Guardrails
- Never install an unreviewed skill or run its scripts automatically.
- Do not bypass permissions, platform protections, or approval gates.
- Do not assume folder conventions are interchangeable across hosts.
- Do not claim activation merely because files were copied.
- Do not expose credentials in setup instructions.

## Verification
- Target host and install scope are known.
- Candidate passed content, safety, and license review.
- Changes are reversible and approved.
- Discovery or manual loading is tested and reported accurately.
