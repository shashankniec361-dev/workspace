---
description: Rules for co-located TypeScript test files
paths:
  - "**/*.test.ts"
  - "**/*.test.tsx"
---

# Test file rules

- Test observable behavior with explicit assertions, including relevant error cases.
- Use shared test-data builders or fixtures for complex objects instead of duplicating large inline objects.
- Do not use snapshot tests for API responses or complex component behavior; assert specific fields and user-visible outcomes.
- Do not use `setTimeout` to coordinate asynchronous tests; await promises and use the test framework's async utilities.
- Keep tests co-located with their implementation and use the `.test.ts` or `.test.tsx` suffix.grep -n -A35 -B5 "def body_has_concrete_convention" tests/test_us02_path_scoped_rules.py