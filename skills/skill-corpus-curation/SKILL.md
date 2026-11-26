---
name: skill-corpus-curation
description: Organize and maintain a large collection of SKILL.md files for reliable discovery, deduplication, metadata consistency, and lifecycle management. Use when building or auditing a reusable agent-skill library.
---

# Skill Corpus Curation

## Objective
Keep a skill library discoverable, internally consistent, maintainable, and free from accidental duplication or misleading metadata.

## Intake workflow
1. Confirm the proposed skill has a distinct purpose and does not duplicate an existing capability.
2. Inspect its frontmatter, name, description, scope, procedures, prerequisites, and expected outputs.
3. Normalize folder and skill names using a consistent lowercase-kebab-case convention.
4. Check for missing references, undeclared dependencies, unsupported tool assumptions, and links that should not be embedded.
5. Review licensing and provenance requirements before accepting third-party material. Preserve required notices; never remove attribution that a license requires.
6. Classify the skill by capability and lifecycle status.

## Catalog fields
Maintain a concise record of:
- Canonical skill name
- One-sentence activation description
- Category and tags
- Supported agent or runtime assumptions
- Dependencies and optional assets
- Version or revision identifier
- Validation status
- Maintenance owner or review date, when applicable

## Deduplication
Compare purpose, activation conditions, inputs, outputs, and procedure—not just filenames. Prefer merging overlapping skills only when their workflows genuinely belong together. Otherwise, clarify their boundaries and add cross-category tags.

## Maintenance cycle
1. Validate frontmatter and directory structure.
2. Check that referenced files exist.
3. Run representative tests for the skill's intended tasks.
4. Detect stale instructions, deprecated interfaces, and incompatible assumptions.
5. Review security, privacy, and license obligations.
6. Update the catalog and record the reason for each change.

## Quality gates
- Every skill has a unique, descriptive name.
- Descriptions explain when to activate the skill.
- No skill depends on an undocumented file or tool.
- Similar skills have explicit boundaries.
- Catalog counts and validation status match the actual repository.
- Required legal notices remain intact.

## Boundaries
Do not claim the corpus is complete based on a partial scan. Report excluded, inaccessible, or unvalidated content explicitly.
