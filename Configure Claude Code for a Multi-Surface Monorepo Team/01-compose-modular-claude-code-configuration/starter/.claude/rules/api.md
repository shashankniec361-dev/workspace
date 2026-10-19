---
description: API handler conventions for the e-commerce monorepo
paths:
  - "src/api/**/*"
---

# API handler rules

- Every API handler must validate request parameters and body fields before calling a repository.
- API handlers must access PostgreSQL through repository modules under `src/db/`; never import or instantiate a database client directly in `src/api/`.
- Return explicit HTTP status codes for success, validation failures, missing resources, and unexpected errors.
- Catch expected errors and return a consistent JSON error response without exposing stack traces or internal implementation details.
- Keep database queries and business logic out of HTTP handlers; delegate them to the appropriate repository or service.