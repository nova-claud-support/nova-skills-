---
name: skill-registry-aggregation
description: Build and maintain a unified catalog from multiple skill collections while normalizing metadata, deduplicating entries, preserving provenance internally, and tracking availability. Use when aggregating skills from different registries or repository collections.
---

# Skill Registry Aggregation

## Objective
Create a consistent, searchable catalog from heterogeneous skill collections without losing important metadata or misrepresenting coverage.

## Workflow
1. Define the catalog scope, supported input formats, update cadence, and inclusion criteria.
2. Enumerate only registries and collections that the current environment can access.
3. Retrieve metadata and skill content using the least-privileged available method.
4. Normalize names, descriptions, categories, tags, versions, and compatibility fields.
5. Validate required metadata and flag malformed or incomplete entries.
6. Compute stable content fingerprints to identify exact duplicates.
7. Detect near-duplicates using normalized names and content similarity; retain distinct variants when behavior differs.
8. Preserve provenance, license status, retrieval time, and version internally for audit and update checks.
9. Separate full-text entries from metadata-only entries and unavailable entries.
10. Generate a catalog with search fields and explicit status labels.
11. Refresh changed entries incrementally and record additions, removals, and updates.
12. Validate catalog counts and sample records after each update.

## Suggested record
- canonical_name
- description
- category
- tags
- compatibility
- version
- content_fingerprint
- license_status
- provenance_record
- last_checked
- availability_status
- duplicate_group

## Guardrails
- Do not invent metadata or claim full registry coverage.
- Do not redistribute skill bodies without appropriate rights.
- Do not discard provenance from internal audit records.
- Do not treat a missing entry as proof that a skill does not exist.
- Keep credentials and private registry data out of the public catalog.

## Verification
- Required fields are validated.
- Exact and near-duplicates are identified.
- Counts reconcile with imported records.
- License and availability states are explicit.
- Updates are reproducible and auditable.
