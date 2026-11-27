---
name: analysis-performance-optimization
description: Diagnose and optimize expensive code-analysis, data-processing, indexing, caching, and agent workflows while preserving correctness, completeness, and traceable evidence.
---

# Analysis Performance Optimization

## Mission
Reduce measured work in an analysis pipeline without changing its externally observable results. A valid outcome may be a small implementation change, a measured configuration adjustment, or a documented decision not to optimize.

## Required inputs
- The user-visible task and expected result.
- The repository revision and working-tree state.
- A representative input, including a small or empty case.
- The relevant runtime, toolchain, operating system, and configuration.
- A correctness oracle independent of the code being optimized.

If any input is unavailable, state the limitation and continue only with work that remains meaningful.

## Workflow

### 1. Establish a baseline
1. Inspect the project instructions and relevant implementation before editing.
2. Record the current revision and uncommitted changes.
3. Select one representative workload and one boundary workload.
4. Run the narrowest relevant correctness tests.
5. Measure only the phases related to the suspected cost: parsing, traversal, lookup, transformation, serialization, I/O, subprocess startup, or cleanup.
6. Record command, environment, input identity, elapsed time, memory where relevant, and exit status.

Do not invent performance numbers or compare non-equivalent workloads.

### 2. Locate the owner of the cost
Trace the public entry point through the implementation to the component that performs the work. Distinguish:
- repeated work from required work;
- CPU cost from I/O and scheduling;
- allocation cost from retained data;
- cold-start cost from steady-state cost;
- actual production work from test-only overhead.

Prefer measurements and call-path evidence over assumptions based on code appearance.

### 3. Select the smallest correction
Consider these patterns only when the baseline demonstrates the corresponding cost:
- Reuse validated immutable results when invalidation is explicit.
- Build an index when repeated lookup dominates and key identity is stable.
- Replace repeated full traversals with a single pass when ordering semantics are preserved.
- Bound pagination or graph traversal when the caller accepts partial results and continuation data is explicit.
- Avoid unnecessary deep copies or repeated parsing when ownership and mutation boundaries are clear.
- Reduce redundant process launches only when lifecycle and isolation guarantees remain intact.
- Cache only deterministic data with a defined key, lifetime, invalidation rule, and privacy boundary.

Never trade away input validation, authorization checks, error reporting, cleanup, or meaningful coverage to obtain a speedup.

### 4. Preserve correctness
Use an independent oracle such as fixed fixture expectations, independently decoded bytes, a reference implementation, or a producer/consumer contract test. Two wrappers around the same faulty implementation are not independent evidence.

Test:
- ordinary, empty, and malformed inputs;
- duplicate keys and ambiguous matches;
- partial and truncated results;
- cancellation and cleanup;
- cache invalidation and stale data;
- permission and identity boundaries;
- concurrency when it is part of the contract.

### 5. Verify the result
1. Re-run the baseline workload with the same environment and options.
2. Run focused regression tests and affected consumer tests.
3. Compare output structure and semantic results, not just exit status.
4. Report measured changes and unmeasured costs separately.
5. Inspect the complete diff for accidental behavior changes.

## Output format
Provide:
- **Finding:** the measured bottleneck or reason no bottleneck was established.
- **Evidence:** revision, workload, commands, and observations.
- **Change:** the smallest correction, or why no change is justified.
- **Correctness:** tests and independent oracle used.
- **Performance:** before/after measurements with environment details.
- **Limitations:** untested providers, workloads, or environmental variables.

## Safety and scope
Do not disable security checks, authorization, audit logging, integrity validation, or cleanup for performance. Do not access systems or datasets outside the user's authorization. Do not claim a speedup from synthetic or non-equivalent measurements.
