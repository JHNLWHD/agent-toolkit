# Local review rules

These rules supplement vendor review skills. User instructions and project
rules take precedence. Keep the vendor files unchanged so plugin updates can
replace them safely.

Use `mattpocock-skills:code-review` as the source for Standards and Spec review
criteria, standards discovery, and its smell baseline when available. Resolve
method integrations through [Maintenance and packaging](maintenance.md#method-integrations).
The rules below adapt
its execution and evidence requirements to local permissions and dirty changes;
they do not define a second review method. Apply the project's severity-first
reporting rule while identifying each finding's axis.

## Code review

Follow [Review council](council.md) for membership, readiness criteria, verdicts,
fix cycles, and reporting in implementation and standalone review. For
implementation, review after required checks and before completion or PR delivery.
Each reviewer applies both of Matt's axes itself. Publishing
comments, requesting hosted review, and submitting approval remain separately
authorized actions. Documentation-only work needs proportionate inline review.

Select the complete candidate surface below. A single-commit comparison is
sufficient only when that commit is the whole requested surface. In a mixed
checkout, give the reviewer a verified task-only candidate or explicit scope
manifest; preserve unrelated changes and identify dependencies on them.

Give the reviewer Matt's review skill, the spec, standards, pinned comparison,
relevant untracked paths, and permission limits. Apply its review criteria within
these local execution rules. Supply requirements and raw evidence without the
coordinator's or implementer's proposed verdict or earlier review conclusions.
Keep the full review log local and include a concise result in the handoff.

Validate findings against the candidate. Fix confirmed in-scope defects when
implementation is authorized, add meaningful regression coverage, rerun affected
checks, then follow the council's re-check rule over the full final surface.
Record the evidence for a rejected finding. Apply the council's stopping rules
and report the actual verdict and remaining work.

Review evidence records the base/head or WIP manifest, reviewer, findings and
disposition, and checks actually run. A changed candidate invalidates prior
clearance. A delegated review is distinct from self-review, hosted Codex review,
and formal GitHub approval. Publish the report only when authorized, then read
back the saved report and verify that it names the reviewed head.

## Implicit state machines

Check affected stateful workflows during implementation planning and review.
An implicit state machine is a lifecycle whose states and transition rules must
be reconstructed from fields and callers. Trace status values, flags, timestamps,
assignment history, token versions, and job claim or retry markers together.

- Identify the meaningful states, valid field combinations, allowed and rejected
  transitions, actor permissions, and business guards. Keep independent lifecycles
  separate, such as delivery status and link validity. Derive time-dependent state.
- Trace each transition through its entry points, writes, required history, and
  external effects. Check transaction ownership, locks, retries, cancellation,
  expiry, and recovery where those paths exist. Preserve server synchronization
  and required effects when moving a rule.
- Use public-operation tests for the relevant risks: accepted and rejected
  transitions, exact time boundaries, required-write rollback, retry limits,
  duplicate execution, or competing operations. Select cases from the workflow;
  a list of state names alone does not verify its behavior.

Use named guards or a small transition table when they clarify scattered rules
or prevent invalid transitions. Keep existing explicit tables and simple flags
when they express the behavior clearly. Finding implicit state does not itself
require a refactor, dependency, stored status, or state-machine framework.

Report concrete failure paths or repeated decisions with file and line evidence.
Distinguish confirmed defects from design suggestions. Keep fixes within the
authorized scope; review-only work still ends with findings.

## PBT, MBT, and test oracles

During planning and review, assess the affected behavior and existing coverage.
Apply the methods below when they add evidence for an in-scope risk. A focused
task does not require a whole-app audit. Planning-only and review-only requests
keep their endpoints; implementation authority permits applicable local tests.

- **Property-based testing (PBT):** use generated inputs when meaningful input
  combinations exceed useful example coverage. Check invariants, round trips,
  idempotency, ordering, isolation, or equivalent transformations. Keep generation
  bounded and repeatable; retain the failing seed and reduce the counterexample.
- **Model-based testing (MBT):** use an independent model when behavior depends
  on command order, history, retries, expiry, or competing lifecycle states.
  Exercise public operations and compare observable state after each command.
  Include relevant rejected commands, duplicates, stale actors, and exact time
  boundaries. A small explicit sequence model can suffice; sequential traces
  do not replace concurrency tests.
- **Test oracles:** establish independent expected results for behavior tests,
  including PBT and MBT. Use approved rules, worked literals, a trusted reference,
  or a justified metamorphic relation. An expected outcome derived from the same
  production table or calculation under test cannot verify that rule's correctness.

Choose the smallest tests that close the gap. Reuse the project's test stack and
sufficient existing properties or sequences; add no framework or dependency just
to label a technique. Preserve applicable dependency approval rules. Keep Matt's
TDD method for behavior changes; tests of already-correct behavior need no
invented red step. When oracle independence is unclear, use a known counterexample
or a reversible test-local fault to check sensitivity.

Put the selected properties, model commands, oracle sources, and relevant limits
in the worker briefs. The reviewer checks their independence and missing risk
coverage, rather than accepting a technique label. Record applied methods and
reproducible evidence in the handoff, or a short reason existing examples suffice
when a material risk was assessed. Finite seeds and traces are bounded evidence,
not exhaustive proof. Unresolved test-boundary choices follow the existing TDD
agreement rule; a technique choice alone adds no approval checkpoint.

## Pin the requested surface

PR and branch reviews cover committed changes. Work-in-progress reviews cover
committed, staged, unstaged, and relevant untracked files. Honor a request
limited to staged or unstaged changes. Inspect both versions when a staged
defect has an unstaged correction.

Resolve an available base with `git rev-parse --verify '<ref>^{commit}'` and pin
the current HEAD SHA. Use discoverable PR or branch metadata when no base is
supplied. Use HEAD for local-only changes. Ask only when the comparison remains
ambiguous. An invalid base stops that comparison.

| Surface | Inspection |
| --- | --- |
| Committed changes | `git diff <base-sha>...<head-sha>` and `git log <base-sha>..<head-sha> --oneline` |
| Staged changes | `git diff --cached <head-sha>` |
| Unstaged changes | `git diff` |
| Relevant untracked files | `git ls-files --others --exclude-standard`; read each selected file |

Check `git status --short` before and after review. An empty committed diff does
not make a dirty checkout empty. Refresh affected evidence when HEAD or the
working state changes. Preserve all existing local changes.

## Use the available evidence

Read `docs/agents/issue-tracker.md` when it exists. Otherwise use the supplied
spec and repository issue or PR metadata. A missing setup file does not block
review. If no spec is available, report that gap and complete the Standards
pass. Ask for a missing spec only when it prevents a material conclusion.

Apply both axes for each council seat. Additional reviewer agents beyond the
council require explicit authorization.

## Stop at the authorized endpoint

Review alone authorizes findings. Apply fixes, submit a review, or perform Git
delivery actions only when the user requests them. Order findings by severity
and include file/line references. Distinguish self-review from independent approval.
