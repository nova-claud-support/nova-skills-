---
name: mcp-integration-engineering
description: Integrate MCP servers as explicit, permissioned interfaces to tools and resources.
---

# Mcp Integration Engineering

## Purpose
Integrate MCP servers as explicit, permissioned interfaces to tools and resources.

## Workflow
1. Inventory server capabilities, transport, authentication, and data access.
2. Grant only required tools.
3. Validate schemas and arguments.
4. Treat responses as untrusted.
5. Keep credentials in secure storage.
6. Set timeouts and response limits.
7. Review versions and dependencies and test upgrades.

## Deliverables
- MCP inventory
- permission matrix
- contract tests
- upgrade checklist.

## Verification
- Confirm scope, constraints, and acceptance criteria.
- Ground decisions in repository evidence.
- Run relevant checks and report exact outcomes.
- Record unresolved assumptions and risks.

## Safety
Do not connect unknown servers to sensitive repositories or grant unrestricted access.

## Completion report
State scope, files inspected or changed, evidence, checks run, outcomes, remaining risks, and approvals required. Never fabricate tool output or test results. Preserve user work and prefer minimal, reversible changes.

## Provenance
Original NOVA SKILLS workflow informed by broad topics in Claude Code Ultimate Guide; not a copied chapter or bundled integration.
