---
name: start-work
description: Scope engineering work through planning, implementation, council review, and verified delivery. Use for /start-work, ticket planning or resumption, feature implementation, or continuing PR work. Planning-only and review-only requests retain their endpoint.
---

# Start Work

Own the contract, phase routing, evidence, and delivery boundary. Keep OpenAI
primary for planning, implementation, and coordination. Use bounded support
workers and the applicable councils through the current runtime. User
instructions and explicit primary-task-only limits take precedence.

## Workflow

1. Read [Contract and permissions](references/contract.md) for every task.
   Establish the outcome, scope, evidence, authority, and completion criteria
   from the request, sources, and current state.
2. For planning, implementation preparation, or resumption, read
   [Planning](references/planning.md). It selects single-owner planning or the
   conditional planning council. A planning-only request ends with the plan
   and its readiness report. For standalone code review, continue at step 4.
3. For authorized code changes, read [Implementation](references/implementation.md).
   Read [Orchestration](references/orchestration.md) before launching workers.
   Use the existing checkout and preserve unrelated changes. Documentation-only
   and formatting-only changes use proportionate inline work.
4. For code implementation or standalone code/PR review, read
   [Local review rules](references/reviews.md) and run its review-council path.
   Standalone review ends with findings and readiness at the requested endpoint.
5. For an authorized delivery action, read [Delivery](references/delivery.md).
   Complete the applicable planning and review gates before dependent delivery.
   Honor explicit scope overrides and report actual coverage.

A material unresolved decision or missing required evidence stops dependent
work. Continue useful independent authorized work. Use `ponytail:ponytail` at
full level when available unless the user selected another level or turned it off.

## Report

Give progress updates about findings, decisions, and blockers. Select relevant
tool fields and preserve required source and visual inspection. Lead planning
with its plan outcome and code work with the council report. Include observed
verification, remaining gaps, candidate identity, and the next authorized action
when applicable. Follow the project's local handoff convention.

When maintaining or preparing this package for a repo, read
[Maintenance and packaging](references/maintenance.md) and [Behavior checks](eval.md).
