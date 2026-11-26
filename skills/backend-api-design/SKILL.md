---
name: backend-api-design
description: Design consistent, secure, documented HTTP APIs with clear validation and error handling.
---

# Backend API Design

## Purpose
Design HTTP APIs that are predictable, maintainable, and secure.

## Workflow
1. Identify consumers, resources, operations, and authorization requirements.
2. Choose resource-oriented routes and consistent HTTP methods.
3. Define request and response schemas, field types, limits, and required values.
4. Validate all input on the server; reject unknown or malformed data where appropriate.
5. Use consistent status codes and structured error responses without leaking stack traces.
6. Enforce authentication and resource-level authorization on every protected operation.
7. Add pagination, filtering, and rate limits where the use case requires them.
8. Document examples, error cases, and versioning policy.
9. Test success, validation failure, unauthorized access, and boundary conditions.

## Validation
- [ ] Every route has a documented purpose and schema.
- [ ] Authorization is checked server-side.
- [ ] Input is validated and output avoids sensitive fields.
- [ ] Errors are consistent and do not reveal secrets.
- [ ] Tests cover expected and rejected requests.

## Safety
Never place API keys or private credentials in frontend bundles, URLs, logs, or example payloads. Store secrets in an appropriate server-side secret store or environment configuration.
