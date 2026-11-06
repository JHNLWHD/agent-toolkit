# Implementation

Use this module for authorized code changes after [Planning](planning.md).
OpenAI owns implementation. Read [Orchestration](orchestration.md) before
launching workers. Explicit primary-task-only requests use inline execution.
For ticket work, also read [Ticket records](tickets.md).

## Implement and verify

1. Use the existing repository checkout; a separate Git worktree requires an
   explicit user request for the task. Confirm the branch/base when applicable
   and existing user changes, including untracked files. Preserve unrelated
   work and existing worktrees. Trace the relevant behavior and callers before
   editing. For affected stateful workflows, apply the
   [implicit state check](reviews.md#implicit-state-machines) before
   implementation. Include the lifecycle rules and test boundaries in the
   implementer's brief. Assess [PBT, MBT, and test oracles](reviews.md#pbt-mbt-and-test-oracles)
   for changed behavior and meaningful risk, even when the user does not name
   them. Include applicable methods, properties or sequences, and independent
   expected results in the brief; retain sufficient existing coverage.
2. Follow the project runtime instructions. For installed-tool work, inspect
   supported CLI commands before proposing changes to that tool's source.
   Before reusing a running service,
   verify its checkout and environment. Reuse it when suitable.
3. Give the implementer the agreed behavior, test boundaries, file ownership,
   project checks, and permission limits. Route features and behavior-changing
   fixes to `mattpocock-skills:tdd`; keep mechanical edits proportionate. Resolve
   material unanswered choices before dependent work. Matt's skill owns the
   implementation method; do not reproduce it here.
   Resolve its availability through
   [Method integrations](maintenance.md#method-integrations).
4. Verify the returned changes and evidence against the contract. Check the
   actual diff, test results, and browser evidence when applicable. Required
   project checks must cover the candidate under review. Missing checks and
   pre-existing failures need explicit evidence; a worker's summary is not a pass.

The candidate is ready for [Review council](council.md) when the scoped changes
and required checks are available for the same pinned surface.
