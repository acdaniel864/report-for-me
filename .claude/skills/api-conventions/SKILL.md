---
name: api-conventions
description: API route conventions. Activated when creating API endpoints, handling requests, or working with API responses.
---

# API Conventions

# TODO: Fill in your project's API patterns. Below is a template.

## Response Format

# TODO: Define your standard response shape. Example:
# All API responses use: `{ success: boolean, data?: T, error?: string }`
# Use helpers from `@/utils/api-response`:
# - `apiSuccess(data)` -- 200
# - `apiError(msg)` -- 500
# - `apiUnauthorized()` -- 401
# - `apiForbidden()` -- 403
# - `apiNotFound()` -- 404
# - `apiValidationError(msg)` -- 400

## Input Validation

- Validate all external input at system boundaries
- Use Zod (or your validation library) for request body, query params, path params
- Return validation errors with specifics (field name, expected format)

## Authentication

# TODO: Define your auth pattern. Example:
# - All API routes require session validation except public endpoints
# - Extract user/org context from authenticated session
# - Never trust client-supplied IDs without verification
