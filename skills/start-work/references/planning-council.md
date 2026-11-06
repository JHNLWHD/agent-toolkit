# Planning council

Read this module when [Planning](planning.md#select-planning-depth) selects a
council. OpenAI owns the plan and final synthesis. Two fresh read-only challengers
examine the plan against the user's goal and the relevant source material.
Use [Model roles](models.md#council-model-preferences) for initial model choices
and [Orchestration](orchestration.md) for dispatch and shared-resource limits.

## Challenge the draft

Give both challengers the same contract, draft plan, inspected source paths,
constraints, acceptance criteria, and verification proposal. Supply known facts
and unresolved assumptions. Each challenger reads the relevant code and source
documents and writes its assessment before reading the other assessment.

- The **technical challenger** examines architecture, domain boundaries,
  dependencies, integration, data and permission rules, failure paths, and
  recovery. It checks whether the proposed verification could detect relevant
  failures and whether the plan accounts for existing callers and old data.
- The **scope challenger** examines whether the approach meets the requested
  need, whether a smaller solution exists, whether exclusions are appropriate,
  and whether acceptance criteria are observable. It tests assumptions about
  dependencies, sequence, ownership, and effort against repository evidence.

Each reports concrete objections, consequences, source evidence, practical
alternatives, and missing decisions. Both may raise concerns beyond their focus.
Challengers perform their own work within the planning endpoint. They make no
implementation edits, branch or worktree changes, database setup, or external
writes. The coordinator gathers authorized inspection evidence when needed.

## Reconcile and finish

The OpenAI owner validates objections, checks disputed facts, and consolidates
one plan. Record each material objection as accepted and resolved, rejected with
evidence, or unresolved. A remaining material objection prevents Ready to
implement. Resolve technical matters from inspected sources or bounded probes
within existing authority. Send business choices to the user with a concrete
recommendation. Gather recoverable missing evidence before handback.

Use one challenge round. A material change to the approach permits one fresh
challenge round for both roles. Keep the count across turns and handoffs.
At that limit, report remaining decisions or blockers. Further rounds require
user direction. Changes to the business outcome or authorization follow
[Contract and permissions](contract.md#permissions).

Use the outcomes defined in [Planning](planning.md#finish-planning). A council
Ready to implement report requires completed assessments from both challengers,
a reconciled plan, verified material assumptions, and no unresolved consequential
objections or decisions. A required unavailable challenger or source produces
Blocked. With an explicit reduced-reviewer or primary-task-only override, report
the requested coverage and keep full-council readiness Unassessed. The plan's
single-owner readiness may still be assessed under [Planning](planning.md#finish-planning).

The planning outcome records plan readiness. Apply the separate implementation
authority before editing. The [Review council](council.md) assesses the resulting
code and verification evidence after implementation.

## Report

Give the user the outcome, chosen approach and reason, challenge coverage,
material objections and their disposition, unresolved decisions, acceptance
criteria, expected verification, and the next authorized action. Link the
canonical plan and detailed challenger records in the local handoff.

Record the plan revision or content hash, each challenger's provider/model and
settings, inspected sources, actual probes, findings, and disposition. Tie the
report to that plan revision. A material approach change invalidates the earlier
readiness conclusion until the permitted re-challenge is complete.
