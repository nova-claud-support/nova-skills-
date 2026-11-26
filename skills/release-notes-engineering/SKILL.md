---
name: release-notes-engineering
description: Prepare accurate, user-focused release notes and changelog entries from verified commits, pull requests, issues, and test evidence while preserving contributor credit and release metadata.
---

# Release Notes Engineering

## Mission
Turn verified engineering changes into concise release notes that explain user impact without overstating shipped behavior. Keep internal provenance separate from public summaries.

## Inputs and boundaries
- Target version and release date, if known.
- The exact commit range or reviewed release candidate.
- Changelog format and repository conventions.
- Permission to edit the changelog or release branch.
- Existing contributor-credit and release-validation rules.

Do not infer the release range from the latest commit alone. Do not publish, tag, push, or edit a release request unless explicitly authorized.

## Workflow

### 1. Establish the release scope
1. Read repository instructions and the current changelog.
2. Identify the target version and exact base/head revisions.
3. Enumerate merged changes in that range.
4. Inspect relevant diffs and linked issue or review context where available.
5. Exclude reverted, abandoned, or unmerged work from shipped-feature claims.
6. Separate code changes, documentation, tests, infrastructure, and maintenance.

Record uncertain authorship, incomplete evidence, and changes whose shipping status cannot be confirmed.

### 2. Classify changes
Group user-visible work into the repository's existing headings, commonly:
- Highlights
- Added or Changed
- Fixed
- Security
- Breaking Changes

Use the project's established vocabulary rather than introducing new sections without reason.

A change belongs in public notes when it materially affects users, operators, compatibility, security, performance, or supported workflows. Internal refactors and test-only changes usually belong in engineering provenance unless they change a user-observable guarantee.

### 3. Write accurate entries
Each entry should answer:
- What changed?
- Who or what is affected?
- What is now possible, fixed, or different?
- Is there a migration, configuration, or compatibility consequence?

Use concrete verbs and observable outcomes. Avoid promotional claims, vague phrases such as “various improvements,” and claims of complete security or reliability.

For breaking changes, state the old behavior, new behavior, affected versions, and migration action. Do not invent a migration command.

### 4. Preserve contributor credit
- Use repository metadata and verified human authorship.
- Retain required issue, pull request, and commit references according to project policy.
- Do not fabricate contributor handles or credit automation as a human.
- Avoid duplicate thanks when one contribution appears in multiple sections.
- Preserve existing credit and formatting conventions.

### 5. Validate
1. Check every statement against a merged change or reproducible behavior.
2. Verify version and date headings.
3. Confirm that reverted changes are not described as shipped.
4. Run the repository's changelog and release-note validators.
5. Review links, spelling, formatting, and duplicate entries.
6. Inspect the final diff and ensure unrelated release metadata was not changed.

## Output
Return the proposed changelog section, the revision range reviewed, validation commands and results, and a short list of unresolved evidence gaps.

## Safety and scope
Never expose secrets, private customer data, vulnerability details that are not approved for disclosure, or internal incident information in public notes. Follow the project's coordinated disclosure process for security fixes. A completed draft is not a published release.
