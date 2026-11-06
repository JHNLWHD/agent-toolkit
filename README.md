# Agent Toolkit

Reusable agent skills for planning, implementation, verification, and delivery.
The workflows produce concise readiness reports backed by source inspection,
checks, and independent review.

## Skills

| Skill | Purpose |
| --- | --- |
| [start-work](skills/start-work/SKILL.md) | Coordinate scoped engineering work with conditional planning challenges, implementation, review councils, and verified delivery. |

## Install and use

Clone the repository with an account that has access.

```sh
git clone https://github.com/JHNLWHD/agent-toolkit.git
cd agent-toolkit
```

In Codex, ask the skill installer to install the package.

```text
Use $skill-installer to install start-work from
https://github.com/JHNLWHD/agent-toolkit/tree/main/skills/start-work
```

Other agents can install the complete `skills/start-work/` directory through
their supported skill mechanism. Keep the reference files with `SKILL.md`.

Invoke the skill with the outcome and constraints you want.

```text
$start-work Plan this feature only. Identify the affected behavior, acceptance
criteria, dependencies, and unresolved decisions.
```

```text
$start-work Implement this ticket using the existing checkout. Give me the
council readiness report and verification evidence.
```

```text
$start-work Review this branch against main and report its readiness.
```

Planning-only requests end with a plan. Standalone reviews end with findings
and a readiness report. Commit, push, publication, merge, and deployment follow
the user's explicit authority. Primary-task-only instructions take precedence.

## Workflow

1. Establish the outcome, scope, evidence, permissions, and completion criteria.
2. Select planning depth. Routine work uses the OpenAI plan owner. Consequential
   or uncertain work adds independent technical and scope challengers.
3. Implement authorized changes and verify the actual candidate.
4. Obtain independent code reviews from the OpenAI, GLM, and DeepSeek seats.
5. Resolve confirmed findings and return the readiness report at the authorized
   delivery endpoint.

Planning reports use **Ready to implement**, **Needs decision**, or **Blocked**.
Code-review reports use **Ready**, **Changes required**, or **Blocked**. Readiness
depends on applicable criteria, evidence, and finding severity. Review records
identify the actual models, candidate, checks, objections, and their resolution.

The user report summarizes delivered behavior, review coverage, verification,
remaining decisions, and the next authorized action. Detailed records follow
the target project's local handoff convention.

## Modules

`start-work` is one installable skill. Its entry point loads the reference
modules needed for the requested task.

| Area | Module |
| --- | --- |
| Scope and authority | [Contract and permissions](skills/start-work/references/contract.md) |
| Planning depth and outcomes | [Planning](skills/start-work/references/planning.md) |
| Technical and scope challenges | [Planning council](skills/start-work/references/planning-council.md) |
| Code changes and verification | [Implementation](skills/start-work/references/implementation.md) |
| Code-review readiness and reports | [Review council](skills/start-work/references/council.md) |
| Review method and evidence | [Local review rules](skills/start-work/references/reviews.md) |
| Git, PR, and release endpoints | [Delivery](skills/start-work/references/delivery.md) |
| Ticket plans and amendments | [Ticket records](skills/start-work/references/tickets.md) |
| Model preferences | [Model roles](skills/start-work/references/models.md) |
| Worker coordination | [Orchestration](skills/start-work/references/orchestration.md) |
| T3 Code tool behavior | [T3 runtime adapter](skills/start-work/references/runtimes/t3.md) |

## Runtime and method integrations

The current defaults keep OpenAI primary and use OpenCode models for bounded
support tasks and independent challenges or reviews. Model choices are
experimental preferences. Check the available models and settings before each
dispatch, and adapt them in the model-role module for your installation.

Council execution requires a runtime with fresh-context delegation and access
to the selected models. T3 Code uses the included runtime adapter. Native
delegation follows the current agent's supported tools and capability rules.

The workflow integrates with `mattpocock-skills:tdd`,
`mattpocock-skills:code-review`, and `ponytail:ponytail` through the installed
skill catalog. Those packages are installed separately. When an integration is
absent, the workflow uses the project's documented method and reports any
remaining evidence gaps.

## Validation and development

Package validation covers skill metadata, relative links and anchors, and
relocation to another installation path. Forward-tests have exercised synthetic
review decisions and a planning-only fixture with an unresolved business choice.
Live end-to-end planning and review councils remain to be exercised.

Before changing a module, inspect its callers and run the affected behavior
checks. Keep model preferences and runtime mechanics in their respective
modules. New skills belong under `skills/<skill-name>/` with a `SKILL.md` entry
point and their required resources.

See [Maintenance and packaging](skills/start-work/references/maintenance.md)
and [Behavior checks](skills/start-work/eval.md) for the validation process.
