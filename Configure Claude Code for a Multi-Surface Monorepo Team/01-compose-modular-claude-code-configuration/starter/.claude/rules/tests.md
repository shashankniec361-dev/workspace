---
description: Rules for co-located TypeScript test files
paths:
  - "**/*.test.ts"
  - "**/*.test.tsx"
---

# Test file rules

- Test observable behavior with explicit assertions, including relevant error cases.
- Use `expect()` assertions to verify returned values and user-visible outcomes.
- Use shared test-data builders or fixtures for complex objects instead of duplicating large inline objects.
- Do not use snapshot tests for API responses or complex component behavior.
- Assert specific response fields instead of checking only that a request succeeded.
- Do not use `setTimeout` to coordinate asynchronous tests.
- Await promises and use the test framework's asynchronous utilities.
- Mock external network calls rather than relying on live services.
- Keep tests isolated so one test's mutations do not affect another test.
- Use descriptive test names that state the expected behavior.
- Keep tests co-located with their implementation and use the `.test.ts` or `.test.tsx` suffix.