---
name: app-analysis
description: Analyze Android application packages and source projects for structure, permissions, dependencies, privacy, security posture, compatibility, and performance. Use for authorized app reviews and defensive assessments.
---

# App Analysis

## Purpose
Produce a reproducible, evidence-based assessment of an application without modifying it or bypassing its protections.

## Supported inputs
- Android APK and AAB packages
- DEX, JAR, and ZIP artifacts
- AndroidManifest.xml
- Android source projects and build files
- Dependency lockfiles and SBOM documents

## Workflow
1. Confirm that the requester owns the application or has explicit permission to assess it. Record the artifact name, version, hash, platform, and assessment scope.
2. Preserve the original artifact. Work on a copy in an isolated analysis environment and do not execute unknown packages on a personal device.
3. Inventory package metadata, SDK levels, application components, exported components, intent filters, signing information, and declared permissions.
4. Review source or decompiled representations for insecure data storage, hard-coded secrets, unsafe WebView configuration, weak transport configuration, insecure cryptography, excessive permissions, and risky component exposure.
5. Inventory dependencies and versions. Identify known end-of-life components and verify findings against trustworthy vulnerability data when available; do not invent CVEs.
6. Review network configuration and API usage from authorized test traffic or source configuration. Never intercept accounts or traffic belonging to other people.
7. Assess privacy behavior: collected data, permissions, local storage, logs, telemetry, retention, and user disclosure.
8. If dynamic testing is authorized, use a disposable emulator or test device with test accounts and synthetic data. Do not evade access controls, extract real user data, or attack production services.
9. Separate confirmed findings from hypotheses. For every finding, include evidence, affected component, impact, severity rationale, reproduction conditions at a safe level, and a remediation recommendation.
10. Re-check fixes and produce a concise report with limitations and tool versions.

## Report format
- Executive summary
- Artifact identity and integrity hash
- Application architecture and component inventory
- Permissions and exported-component review
- Dependency inventory
- Security and privacy findings
- Compatibility and performance observations
- Remediation plan ordered by risk
- Scope limitations and unverified assumptions

## Quality gates
- Never claim a vulnerability without supporting evidence.
- Do not treat a declared permission alone as proof of malicious behavior.
- Do not expose secrets, tokens, personal data, or private endpoints in reports.
- Distinguish static-analysis indicators from confirmed runtime behavior.
- Keep all testing within the authorized scope and use synthetic test data.
