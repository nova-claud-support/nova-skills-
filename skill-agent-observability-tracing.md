---
name: agent-observability-tracing
description: Instruments agent workflows with privacy-aware traces, structured events, latency and cost measurements, and failure attribution. Use when debugging multi-step agents, monitoring tool use, or improving reliability in production workflows.
---

# Agent Observability and Tracing

## Objective
Make agent behavior diagnosable through structured evidence while minimizing sensitive data collection.

## Workflow
1. Define the operational questions: where time is spent, which tools fail, why tasks stop, and whether outcomes meet acceptance criteria.
2. Establish a trace per user task and spans for planning, model calls, tool calls, validation, and handoff.
3. Give each span a stable operation name and record start/end time, status, retry count, and safe error category.
4. Track relevant metrics: completion rate, tool error rate, latency percentiles, retry frequency, token or compute usage, and validation failures.
5. Record structured events with correlation IDs. Avoid logging full prompts or raw user payloads by default.
6. Redact secrets and minimize personal data before telemetry leaves the execution boundary.
7. Distinguish model output, tool result, validation result, and final user-visible outcome.
8. Add explicit checkpoints around state-changing operations so partial completion can be diagnosed.
9. Use traces to identify bottlenecks and recurring failure modes; prioritize fixes by user impact and frequency.
10. Set retention and access controls appropriate to the sensitivity of the telemetry.

## Event fields
Recommended fields include:
- trace_id and span_id
- task_type and operation
- start_time and duration
- status and safe_error_code
- tool_name and retry_count
- validation_status
- resource_usage, when available

## Guardrails
- Do not log API keys, passwords, access tokens, or private user content unnecessarily.
- Do not interpret correlation as causation.
- Do not use telemetry as a substitute for functional tests.
- Do not report metrics that were not actually measured.

## Verification
- A failed task can be traced to a stage without exposing secrets.
- Metrics have defined units and collection windows.
- Trace identifiers correlate related events.
- Retention and access policies are documented.
