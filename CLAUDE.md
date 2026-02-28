# CLAUDE.md

## Project Overview

<!-- TODO: Describe your project in 2-3 sentences. What it does, what stack it uses. -->
<!-- Example: MyApp is a [type] application built with [framework, language, database]. Deployed on [platform]. -->

## Critical Policies

<!-- TODO: List non-negotiable rules that every agent (human or AI) must follow. -->
<!-- These get enforced by hooks in .claude/settings.json but should also be stated here. -->
<!-- Examples: -->
<!-- - Never commit secrets or credentials -->
<!-- - All database queries must be scoped to [tenant/org/user] -->
<!-- - No mock data in production code -->

## Architecture

### Project Structure
```
# TODO: Map your project's directory layout
src/
├── app/           # Pages and API routes
├── lib/           # Core logic
├── components/    # React components
└── types/         # TypeScript types
```

### Key Conventions
<!-- TODO: Import aliases, response patterns, validation approach, key dependencies -->

## Commands

```bash
# Development
npm run dev

# Build & Validation
npm run build
npm run lint

# Tests
npm test
```

## Testing

See `.claude/skills/testing-patterns/` for conventions and coverage requirements.

<!-- TODO: Add test inventories if you have them -->
<!-- Inventories: @tests/docs/test-plan.md | @tests/docs/coverage.md -->

## Working Style

### Task Management
1. Write plan to `tasks/todo.md` with checkable items
2. Check in before starting implementation
3. Mark items complete as you go; add review section when done

### Non-Trivial Changes
For API integrations, schema changes, auth/security, core workflows:
1. **Impact & Risk**: Identify affected areas/dependencies. If uncertain, STOP and ask.
2. **Design & Approach**: Describe proposed solution. Confirm alignment with existing patterns.
Do NOT write code until both steps are complete.

### Subagent Strategy
See `.claude/skills/subagent-strategy/` (2-4 agents typical, parallel when independent).

### Self-Improvement Loop
After ANY correction: update `tasks/lessons.md` with the pattern. Review lessons at session start.

## Custom Triggers

- **`qc`**: 3-iteration deep review -- (1) correctness, (2) architecture, (3) security/performance
- **`runit`**: Execute all remaining steps without pausing. Only stop when fully implemented, tested, and production ready.
- **`name <label>`**: Set terminal tab title. Run: `echo -ne "\033]0;<label>\007"` via Bash.

## Compaction
When compacting, always preserve: the full list of modified files, any test commands that need to run, and the current task plan.
