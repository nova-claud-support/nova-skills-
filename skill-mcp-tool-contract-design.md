---
name: mcp-tool-contract-design
description: Design and review reliable tool interfaces for agents, including input schemas, result contracts, error semantics, pagination, evidence, permissions, and lifecycle boundaries.
---

# Agent Tool Contract Design

## Mission
Create tool interfaces that are predictable for both models and humans. A tool contract must define what the tool does, what it may change, what evidence it returns, and how callers recover from failure.

## Workflow

### 1. Define the user task
Write the concrete task the tool should support and identify:
- the actor and required authorization;
- the resource or target;
- the intended side effects;
- the expected result;
- the information that must remain private;
- the conditions under which the tool must refuse or stop.

Do not begin with a schema before the task and boundary are clear.

### 2. Choose the tool boundary
Prefer one tool for one coherent operation. Separate read-only inspection from mutation, and separate planning from applying changes when approval matters.

Reuse an existing tool when it already provides the required semantics. Avoid thin wrappers that add no meaningful validation, safety, or result value.

### 3. Design inputs
- Use explicit names and stable types.
- Make required fields genuinely required.
- Give optional fields safe defaults.
- Reject unknown or malformed values where ambiguity could cause harm.
- Use bounded strings, arrays, page sizes, traversal depth, and execution duration.
- Avoid redundant unions and deeply nested schemas when a flat contract is sufficient.
- Represent paths and identifiers unambiguously.
- Never ask callers to pass credentials in ordinary tool arguments when a secure credential mechanism exists.

### 4. Design results
Return structured data that distinguishes:
- completed results;
- partial results;
- empty results;
- validation failures;
- authorization failures;
- retryable infrastructure failures;
- permanent configuration failures.

For partial results, include the reason, scope examined, omitted scope, and a continuation mechanism when supported. Do not make absence claims from an incomplete search.

For evidence-backed tools, include source identity, relevant observations, limitations, and stable references where available. Separate observed facts from inferred explanations.

### 5. Define side effects and recovery
Document whether the operation reads, writes, launches, attaches, deletes, publishes, or contacts a remote service. State whether retries are safe and whether the operation is idempotent.

For mutating operations:
1. validate the complete request;
2. show or record the intended change;
3. require the necessary approval;
4. apply the smallest authorized change;
5. verify the resulting state;
6. report rollback or cleanup status.

Do not silently retry a mutation whose outcome is unknown.

### 6. Review agent usability
Test the advertised description and schema with representative user requests. Check whether an agent can select the correct tool, provide valid arguments, interpret partial results, and avoid claiming unsupported conclusions.

Descriptions should state purpose, target scope, prerequisites, side effects, and important limits without duplicating the entire manual.

### 7. Verify the contract
Create tests for:
- valid and invalid inputs;
- missing permissions;
- empty and large results;
- pagination and truncation;
- partial provider failures;
- cancellation and timeout;
- duplicate requests and idempotency;
- cleanup failure;
- secret redaction.

Run schema validation, documentation checks, and relevant integration tests. Confirm the implementation and advertised schema match.

## Deliverable
Provide the proposed boundary, input and output examples, error model, side-effect classification, authorization model, evidence semantics, alternatives considered, and verification plan.

## Safety
Default to least privilege and read-only behavior. Never design a tool that hides its side effects, exfiltrates secrets, bypasses user approval, or executes arbitrary commands without a bounded and authorized purpose.
