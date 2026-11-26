---
name: authorized-app-reverse-analysis
description: Perform defensive, authorized analysis of software packages and application behavior for compatibility, debugging, security review, interoperability, and software preservation.
---

# Authorized Application Reverse Analysis

## Mission
Explain observable behavior of an application the user owns or is explicitly authorized to examine. Produce evidence-based findings that support debugging, compatibility, secure maintenance, and learning.

This skill is not permission to access third-party systems, defeat access controls, extract private data, or develop exploits.

## Authorization gate
Before analysis, confirm that the target is:
- software the user owns or maintains; or
- a sample, lab, or package supplied for authorized study; or
- an application covered by explicit written authorization.

If authorization is unclear, limit assistance to general concepts, public documentation, or a harmless sample. Do not proceed with intrusive runtime actions.

## Define the question
Record:
- target type and version;
- the exact behavior or compatibility question;
- local files and evidence supplied;
- permitted analysis methods;
- prohibited actions and data classes;
- expected deliverable.

Prefer the least invasive method that answers the question.

## Safe analysis workflow

### 1. Preserve the sample
1. Work on a copy and retain the original unchanged.
2. Record file name, size, type, version metadata, and cryptographic hash.
3. Use an isolated workspace with no unnecessary network access.
4. Do not execute unknown packages on a personal or shared device.
5. Record tool versions and analysis settings.

### 2. Start with static inspection
For application packages, inspect only what is needed:
- package metadata and declared components;
- permissions and exported entry points;
- resources, assets, and localization;
- dependency and library inventory;
- signing identity and integrity metadata;
- configuration files and embedded version information.

For source or script bundles, map modules, imports, public interfaces, and dependency boundaries. For native binaries, use read-only metadata and disassembly views to understand file structure and program layout.

Do not attempt credential recovery, private-key extraction, license circumvention, DRM removal, or authentication bypass.

### 3. Form evidence-based hypotheses
For each observation:
1. State the question.
2. Identify the exact artifact, file, symbol, or documented behavior examined.
3. Separate direct observations from interpretations.
4. Record alternative explanations.
5. Mark unknowns explicitly.

Do not treat a missing string, symbol, permission, or endpoint as proof that a behavior is impossible.

### 4. Observe behavior only in an authorized lab
If static evidence is insufficient, use a disposable emulator, local test application, or isolated lab instance. Prefer ordinary user-visible workflows and documented debug interfaces.

Capture only the minimum data needed to answer the question. Redact tokens, personal information, session identifiers, private URLs, and customer data from reports.

Do not attach to unrelated processes, intercept another person's communications, evade monitoring, or alter a third-party service.

### 5. Validate the conclusion
Use at least one independent check where practical:
- compare two versions of an owned application;
- reproduce the behavior in a minimal test project;
- compare package metadata with the app's documented configuration;
- validate a suspected issue using a harmless local fixture;
- test a compatibility fix against the affected supported versions.

Do not present a hypothesis as a confirmed vulnerability without a safe, authorized reproduction and clear impact evidence.

### 6. Recommend remediation
Prioritize defensive actions:
- remove unnecessary permissions and exported components;
- protect sensitive local data;
- validate inputs and trust boundaries;
- update vulnerable dependencies;
- improve signing, integrity, and release configuration;
- add regression tests;
- document compatibility constraints.

When discussing a security weakness, focus on impact, affected component, evidence, and remediation. Avoid operational exploit instructions.

## Report format
1. **Scope and authorization**
2. **Target identity** — version, hash, package type
3. **Methods** — static or lab-only runtime inspection
4. **Findings** — severity, evidence, confidence, affected component
5. **Limitations** — unavailable symbols, incomplete coverage, untested versions
6. **Remediation** — prioritized and testable actions
7. **Reproduction boundary** — safe local test conditions only

## Stop conditions
Stop and ask for clarification if the target appears to be outside the authorized scope, the task shifts toward bypassing access controls, or requested data includes credentials or private user information. Do not provide instructions for weaponizing a finding, persistence, stealth, evasion, or unauthorized access.
