# Orchestration

Start-work owns scope, coordination, evidence, and delivery. The current runtime
owns agent launch and communication. Method integrations follow
[Maintenance and packaging](maintenance.md#method-integrations).

## Launch

Before selecting workers, read [Model roles](models.md) for the OpenAI primary,
support tasks and council model preferences. Use the roles selected by
[Planning council](planning-council.md), [Implementation](implementation.md), or
[Review council](council.md). Batch useful support work into bounded tasks and
delegate it when it saves work or adds evidence.
Use the existing checkout. Create or switch worktrees only when the user
requests them. Keep worker IDs and candidate identity with the evidence.
For Codex native children, use `spawn_agent` with `fork_turns: "none"` and wait
with the native completion tool. Follow the runtime's delegation rules.

When running in T3 Code, read the [T3 runtime adapter](runtimes/t3.md) before
selecting or launching workers. Other runtimes use their supported delegation
tools and capability discovery.

## Worker boundaries

Workers report to this coordinator and perform their own work. The selected
planning council, code-review council, and scoped support workers are part of
this workflow. Additional implementation workers, committees beyond these
councils, and parallel editing require user authorization.

If no delegated execution is available, complete permitted preparation and report
the missing capability. Do not silently take over implementation. Explicit
primary-task-only requests instead use inline implementation and review, with
the lack of independent review reported.

## Brief

Give every worker a self-contained brief with:

- Task, acceptance criteria, exclusions, and agreed test boundaries.
- Role, selected provider/model/settings, and required tools or input modalities.
- Repository, current branch/base, task-owned files, and pre-existing changes.
- Applicable instruction/spec/standards paths and the owning vendor skill.
- Allowed edits, tests, Git actions, external actions, and stopping conditions.
- Required output: changed paths, actual checks and results, evidence locations,
  decisions, unresolved risks, and final candidate identity.

Keep implementation authority separate from commit, push, publication, merge,
and deployment authority. Internal worker messages are part of coordination;
this grants no permission to contact people or publish to external services.
Keep delivery actions with the coordinator unless their delegation is explicit.

Use the selected council's brief and evidence rules for challengers or reviewers.
Each worker must examine its required sources and verification boundaries.

## Shared resources

Before edits, record task ownership and detect other active writers. Serialize
overlapping files, database setup, shared assets, and browser-test resources.
Use a separate local test database per concurrent task where supported. Preserve
other tasks' processes and changes. Do not create infrastructure to solve a
collision when serialization is enough.

## Verify and resolve

Read the returned diff and logs; compare each acceptance criterion with evidence.
Verify that required checks ran against the candidate being reviewed. Read UI
evidence when relevant. Reproduce material findings or inspect the supporting
path before accepting or rejecting them. Never equate tests with exhaustive
coverage, formal approval, deployment, or acceptance.

For code work, fix small confirmed in-scope findings in the primary task. For larger fixes,
launch a fresh implementer with the confirmed findings and current candidate.
Verify affected checks, then follow the council's re-check and cycle rules.
Follow the selected runtime's rules for fresh reviewer tasks.
Keep the prior reports in the local handoff. Report out-of-scope findings and
retain the authorized fix boundary.

Use the [council report](council.md#report) for implementation and code review.
