---
name: subagent-strategy
description: Subagent orchestration patterns. Activated when planning parallel work, spawning subagents, or coordinating multi-agent tasks.
---

# Subagent Strategy

## When to Use Subagents

Use 2-4 agents for non-trivial tasks. More agents = more context overhead. Fewer = sequential bottleneck.

## Parallel vs Sequential

**Parallel** when agents are independent:
- Different file zones (frontend vs backend vs tests)
- Research tasks with no shared output
- Independent feature implementations

**Sequential** when output feeds the next step:
- Architecture research -> implementation
- Schema change -> API update -> UI update

## File Isolation

Parallel agents must NEVER edit the same file. Define zones before spawning:
- Frontend: `src/components/`, `src/app/(pages)/`
- API/Backend: `src/app/api/`, `src/lib/services/`
- Data layer: `src/lib/db/`
- Tests: `tests/`

If two agents need the same file, run them sequentially.

## Background vs Foreground

- **Foreground**: when you need results before continuing
- **Background**: for research, exploration, or independent validation

## Anti-Patterns

- Spawning agents that duplicate work the parent is already doing
- More than 4 concurrent agents (diminishing returns)
- Agents with overlapping file zones
