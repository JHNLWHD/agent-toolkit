# Ticket records

Use these rules with `start-work` for ticket planning, implementation, and
resumption. [Contract and permissions](contract.md) owns authority and
[Planning](planning.md) selects the planning depth. This module owns ticket
source verification, canonical records, plan status, and amendments.

## Verify the source

Read the ticket and the directly referenced tickets before relying on their
claims. Verify material design claims against the relevant code and callers.
Cite the inspected ticket or `file:line`. Mark inaccessible references and
unsupported claims as unverified. Ask for missing evidence only when it blocks
the requested work.

## Save the plan

For substantial ticket work, save the plan before implementation. Reuse the
project's plan location when it exists. Otherwise use
`.agents/handoffs/<TICKET-ID>/plan.md` in the target repository. Keep these
records local and untracked unless publication is requested.

For work across repositories, keep one canonical plan in the primary repository.
Record its absolute path in the other repositories' handoff notes. Use a
filesystem-safe ticket key. Qualify issue numbers with the repository name when
needed to prevent collisions.

Read an existing plan before proposing changes. Record:

- The ticket, repository paths, acceptance criteria, and requested endpoint.
- The current and proposed behavior, with code references. Add a diagram or
  comparison table when it makes a material behavior change easier to assess.
- Real design choices, tradeoffs, and a recommendation. State the reason for a
  single approach when there is only one useful option.
- Expected files and a reason for each change, exclusions, and verification.
- The branch, base, authorized actions, and unresolved decisions for each
  repository. Distinguish proposed state from observed state.

A small ticket with no material design choice can use the work contract already
in the handoff. Review-only work uses the existing plan as evidence and does not
create an implementation plan.

## Preserve decisions

The plan records authority; its existence or status does not grant authority.
Use `Status: draft` while a required decision or approval is pending. Use
`Status: approved YYYY-MM-DD` only after the user approves that plan. If the user
has already authorized implementation without a plan checkpoint, record
`Status: implementation authorized YYYY-MM-DD` and proceed within that scope.

Honor the checkpoint in the request or project rules. A planning-only request
ends with the saved plan. Offer `$grilling` when an unresolved design choice
would benefit from it; use it only when the user requests it. Continue in the
same chat after approval unless the user requests another chat or a handoff.

Preserve the approved plan text. Append a dated `## Amendment: YYYY-MM-DD` when
the approach changes. Record the cause and whether the change is authorized or
pending. Resolve a change that exceeds the authorized scope before implementing
it. A resumed task reads the plan, amendments, and current repository state.

## Save the outcome

At a natural stopping point, update `handoff.md` beside the plan. If a project
already has a canonical handoff location, update that record and link the plan.
Include only applicable fields:

- Per-repository branch, base, changed files, and staged or committed state.
- Final changes and the reasons for material decisions, with code references.
- Exact verification commands, observed results, required services, unavailable
  checks, and evidence for any pre-existing failure. Exclude secret values.
- Differences from the approved plan and the cause of each difference.
- Remaining risks, next checks, and delivery status. Include deployment order
  for dependent repositories and observed deployment evidence when available.

Prepare a correction if the final behavior differs from the ticket description.
Publish it only when ticket updates are authorized. A handoff must describe the
final state, including any review changes and any work that remains local.
