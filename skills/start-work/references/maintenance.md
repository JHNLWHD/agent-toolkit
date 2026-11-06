# Maintenance and packaging

The installable unit is the complete `start-work/` directory. `SKILL.md` routes
tasks to reference modules. Each module owns its named phase or policy and
reaches shared rules through relative links. Keep the skill's directory layout
when copying it into a personal skills repo or installing it elsewhere.

## Method integrations

Resolve `mattpocock-skills:tdd`, `mattpocock-skills:code-review`, and
`ponytail:ponytail` by name from the current skill catalog. Ponytail's level is
a separate choice from its catalog name. Keep implementations with their own
packages. If a method integration is absent, use the project's documented test
or review method within the same scope and report the missing integration.
Required council membership, evidence, permissions, and readiness gates still
apply. An assessment that lacks required evidence stays Unverified.

Worker execution requires the matching runtime's delegation tools and available
model routes. An unavailable required worker follows the capability rules in
[Orchestration](orchestration.md). Model and provider preferences are localized
in [Model roles](models.md). T3-specific tool behavior is in the
[T3 runtime adapter](runtimes/t3.md).

## Validate before distribution

Run the installed skill-creator validator when available and the affected
[Behavior checks](../eval.md). Verify every local link and heading anchor.
Copy the skill folder to a temporary location and verify those links again.
Inspect for absolute installation paths, credentials, private project content,
and generated handoff or evaluation artifacts. Distribute only owned skill files.

For a forward-test, record the evaluator's actual provider/model separately
from simulated scenario roles. An evaluator may exercise planning decisions
under an explicit test-model selection. Report which production roles and
runtime paths were exercised and which were simulated.

Preserve runtime and dependency boundaries when editing modules. Read the
affected callers and check each route's completion criteria. A future repo may
add its own installation guide, license, and release process. Perform repo
creation, commits, pushes, or publication under their own explicit authority.
