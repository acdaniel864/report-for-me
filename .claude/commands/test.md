---
description: Run the appropriate test suite for recent changes
---
Analyze the files changed in this session and run the appropriate tests:

1. Check `git diff --name-only` for changed files
2. Route to the right test runner based on file paths:
   - Backend code (`src/lib/`, `src/app/api/`): run Jest
   - Frontend code (`src/components/`, `src/app/(pages)/`): run Playwright or component tests
   - Other: run the full test suite
3. Report results and any failures

# TODO: Adjust the test runner commands for your project:
# - Jest: `npx jest --config tests/jest.config.js <path>`
# - Playwright: `npx playwright test <path>`
# - Full suite: `npm test`
