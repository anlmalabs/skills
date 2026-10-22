---
name: implement
description: "Implement a piece of work based on a spec or set of tickets. Modes: simple (default), agents (subagent orchestration), spec (implement a /to-spec + /to-tickets result). Use when implementing a ticket, spec, or feature."
disable-model-invocation: true
---

Implement the work described by the user in the spec or tickets.

If the user passes a ticket reference, fetch it from the issue tracker and state its title before starting. If the reference is ambiguous, ask.

Call the Skill tool with "tdd" where possible, at pre-agreed seams.

Run typechecking regularly, single test files regularly, and the full test suite once at the end.

Once done, call the Skill tool with "code-review" to review the work.

Commit your work to the current branch.

## Modes

- **Simple (default):** implement directly as above.
- **Agents mode (subagent orchestration):** read `references/agents.md` (merged from implement-agents) and follow it as orchestrator.
- **Spec mode (implement a /to-spec + /to-tickets result):** read `references/spec.md` (merged from implement-spec) and follow its ticket-graph workflow.

Choose agents mode when parallel subagents are warranted; spec mode when a spec with tickets exists.
