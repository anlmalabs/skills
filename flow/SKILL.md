---
name: flow
description: "Single entry point for all work. Triage any request to the right skill or workflow: frame, plan, spec, tickets, implement, debug, review, verify, wayfinder, slop/audit, or a domain skill. Use when starting any task, unsure which skill applies, or wanting one place to route work."
---

# Flow (unified router)

One entry point. Pick the row that matches the request and invoke that skill. When two rows match, the more specific one wins; when unsure, ask one clarifying question.

## Routing

| Signal in the request | Invoke |
|---|---|
| Raw request, no work started, need goal/acceptance/scope | `frame` |
| Need to stress-test a plan/decision | `grilling` (docs mode if ADRs/glossary needed) |
| Need a domain model / glossary / ADR | `domain-modeling` |
| Need module/interface design vocabulary | `codebase-design` |
| Huge work spanning multiple sessions | `wayfinder` |
| Need an execution shape / slices / ordering | `plan` |
| Synthesize discussion into a spec | `to-spec` |
| Break into tickets | `to-tickets` |
| Triage issues/PRs | `triage` |
| Orchestrate dependent sub-issues | `issue-chain` |
| Implement a ticket/spec/feature | `implement` (simple/agents/spec mode) |
| Bug, failing test, stack trace, regression | `debug` |
| Build feedback loop for hard bug | `debug` → `references/feedback-loop.md` |
| Review a branch/PR (standards + spec) | `code-review` |
| Review for slop/unchosen defaults | `review` (slop review) or `zeroslop` router |
| Audit copy/UI/code/commits/config/a11y/integrity/skill | `zeroslop` (routes to references) |
| Prove work is done (fresh evidence) | `verify` |
| Commit/PR message hygiene | `secure`? no → `zeroslop` references/commit.md |
| Git isolation, branch, worktree, cleanup | `git` |
| Secrets, supply chain, destructive commands | `secure` |
| Context budget / spilling / compaction | `context` |
| Persist knowledge across sessions | `memory` |
| Long-running/repeating task | `loops` |
| Delegate to sub-agents | `delegate` |
| Credential/env/tooling design | `harness` |
| Author/edit a SKILL.md or AGENTS.md | `skill-authoring` |
| Research a question | `research` |
| Throwaway prototype | `prototype` |
| Test-first development | `tdd` |
| Write a PR body | `pr` |
| Retrospective | `retro` |
| Handoff to another agent | `handoff` |
| Teach/learn a concept | `teach` |
| Generate a bash wizard | `wizard` |
| Writing docs for agents | `writing-for-agents` |
| Find/install skills | `find-skills` |
| Setup repo for engineering skills | `setup-matt-pocock-skills` |
| Improve codebase architecture | `improve-codebase-architecture` |

## wayfinder vs zeroslop

- Use `wayfinder` when work is bigger than one session and needs a shared map of decision tickets.
- Use `zeroslop` when auditing or routing an agentic workflow decision (frame/plan/delegate/verify/debug/review/secure/persist).
- They compose: wayfinder plans the map; zeroslop skills execute each node.

## Rule

Frame before planning, plan before implementing, verify before claiming done, review before merging.
