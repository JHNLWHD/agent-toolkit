# Planning

Use this module for planning, implementation preparation, and resumption.
Read [Contract and permissions](contract.md) first. For ticket work, read
[Ticket records](tickets.md) and reuse the canonical plan and amendments.
Planning-only work uses source inspection and plan records. Any additional
setup or probe follows the user's specific authority and checkpoints.

## Inspect and draft

Trace the relevant code, callers, domain rules, and existing workflow. Separate
observed behavior from proposed behavior and identify material unknowns.
For stateful or risky changes, read the relevant sections of
[Local review rules](reviews.md#implicit-state-machines) and
[PBT, MBT, and test oracles](reviews.md#pbt-mbt-and-test-oracles) before setting
the implementation and verification boundaries.

The OpenAI plan owner drafts the smallest approach that satisfies the contract.
Include the changed behavior, acceptance criteria, exclusions, dependencies,
file ownership, verification boundaries, and material decisions. Compare real
alternatives when a choice affects cost, behavior, or recovery. Scale the plan
to the task and use existing project patterns.

## Select planning depth

Use the [Planning council](planning-council.md) when the user requests it, or
when a material choice or unresolved assumption affects one of these areas.

- Architecture or domain-model boundaries.
- Data integrity, authorization, concurrency, or recovery.
- Multiple repositories or dependent changes.
- Conflicting requirements or materially different approaches.
- Repeated implementation failures that suggest the plan needs revision.

A routine change with a clear requirement, established pattern, and known checks
can proceed with the OpenAI plan owner. A high-impact change merits challenge
even when the proposed approach looks straightforward. Record the reason for
the chosen planning depth in the plan or handoff. Explicit primary-task-only
and reduced-reviewer instructions take precedence.

## Finish planning

Planning is ready when the approach, scope, acceptance criteria, ownership,
dependencies, verification, and applicable recovery path are clear, with material
assumptions verified and consequential objections resolved. If a council ran,
include its report and use its outcome. Otherwise give the same outcome with
single-owner coverage.

- **Ready to implement** means the plan is sufficiently defined to start.
- **Needs decision** identifies a business choice or consequential tradeoff for
  the user, with options, a recommendation, and the effect on scope or delivery.
- **Blocked** identifies a missing required fact, access, or dependency.

Record implementation authority separately using [Contract and permissions](contract.md#permissions)
and, for tickets, [plan status](tickets.md#preserve-decisions). A planning-only
request ends with the plan and report. When implementation is already authorized
and any required checkpoint is satisfied, continue to [Implementation](implementation.md).
On resumption, inspect the current repository and plan amendments. Reassess
material changes before dependent implementation.
After a user decision, reassess remaining material facts and prerequisites
before marking the plan Ready to implement. Record any facts still requiring
inspection and their effect on dependent work.
