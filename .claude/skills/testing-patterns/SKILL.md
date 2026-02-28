---
name: testing-patterns
description: Testing patterns and conventions. Activated when writing tests, creating mocks, running test suites, or debugging test failures.
---

# Testing Patterns

# TODO: Fill in your project's testing conventions. Below is a template.

## Test Framework

- **Unit/Integration**: Jest (or your framework)
- **UI/E2E**: Playwright (or your framework)

## Conventions

- **File naming**: `{module-name}.test.ts` -- matches the source file name
- **Mock pattern**: Module-level `jest.mock()` at top, configure in `beforeEach`
- **No mock data in production**: Tests mock at the boundary, never in production code

## Running Tests

```bash
# Full suite
npm test

# Specific domain
npx jest --config tests/jest.config.js tests/path/to/domain/

# UI tests (requires dev server)
npx playwright test tests/ui/
```

## Coverage Requirements

- **Critical paths** (auth, security, data layer): every code path and error case
- **Standard** (business logic, API routes): happy path + key error cases
- **Low risk** (UI, config): Playwright or integration tests only

## Helpers

# TODO: List your test helpers, fixtures, and mock utilities here.
# Example:
# - `tests/utils/fixtures.ts` -- standard test IDs and constants
# - `tests/utils/mongodb-mock.ts` -- `createMockCollection()` helper
