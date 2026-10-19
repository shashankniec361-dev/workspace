---
description: API handler conventions for the e-commerce monorepo
paths:
  - "src/api/**/*"
---

# API handler rules

- Validate all request parameters and body fields before processing a request.
- Use `req.params` for route parameters and `req.body` for submitted payloads.
- Keep HTTP handlers focused on request validation, service calls, and response construction.
- Access PostgreSQL through repository modules under `src/db/`; never instantiate a database client inside `src/api/`.
- Return `400` for invalid input and `404` when a requested resource does not exist.
- Return appropriate `201` or `200` status codes for successful resource creation or retrieval.
- Catch expected errors and return consistent JSON error responses.
- Never expose stack traces, SQL queries, credentials, or internal implementation details to clients.
- Keep database queries out of API handlers and delegate persistence to repository modules.
- Use `async`/`await` for asynchronous repository calls and handle rejected promises explicitly.
- Ensure each response is sent once; do not send a second response after an error has been handled.
- Follow the shared API conventions in `@.claude/standards/api.md` and avoid introducing incompatible response shapes.