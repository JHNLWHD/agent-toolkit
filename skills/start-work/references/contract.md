# Contract and permissions

Read this module before planning, editing, reviewing, or delegating work.

## Establish the contract

1. Read applicable `AGENTS.md` and the relevant context, domain, and workflow
   documents before proposing scope. Use relevant conversation history and
   memory; current instructions and project evidence take precedence.
2. Extract known answers from the request. Inspect the target repository, issue,
   or PR to fill factual gaps. The user does not need to say `discover`.
3. For bare `/start-work`, use the target and outcome established in context.
   Ask one focused question only when missing information affects scope,
   correctness, or authority. Continue independent authorized work while waiting.
4. Use **Outcome · Scope/exclusions · Evidence · Constraints · Authorized
   actions · Done/verification** to resolve ambiguous work. State only missing
   or changed contract details; a clear request needs no confirmation round.

For PR work, identify the requested endpoint: findings, local fixes, pushed
changes, a submitted review, or a merge. For feature work, identify the changed
user behavior and acceptance criteria. Planning or review alone does not
authorize implementation. Honor explicit project phase and approval gates.

For work across repositories or a feature stack, record the feature, repository,
branch, base, commit authority, and delivery endpoint in the existing handoff
before editing. Distinguish planned branches from created branches. Update the
map when scope or authorization changes; ask only about unresolved authority.

## Permissions

Use authorization already given in the conversation for the same scope.
Implementation requests authorize the necessary local edits and verification.
Commit, push, publish review results, request hosted review, submit approval,
merge, deploy, and send messages to people are distinct actions; perform each
only with explicit user authorization. Scoped internal worker coordination is
part of this workflow.
Approval for one action does not grant the others.

When the user sets a checkpoint, stop before every operation it covers,
including branch, worktree, or database setup. Apply `apply` or `approve` to the
pending proposal and its stated scope. A checkpoint is required only when an
applicable instruction establishes one.

Complete authorized preparation before asking about a pending external action,
so the user can approve a concrete result. Ask at that boundary only if authority
is missing. If an instruction blocks work, cite its file and exact rule and
explain the blocked action; do not infer an approval gate from a preference.
