# Model roles

Keep OpenAI as the primary model for coordination, planning, architecture,
implementation, test design, defect fixes, and final decisions. Preserve the
user's selected OpenAI model. Support delegation supplements that work.
Explicit model choices override these preferences. A primary-task-only request
controls delegation and preserves the selected provider/model. Record actual
model identity for every role. Report a mismatch with a required model before
dependent work and follow the runtime's availability rules.

## Support tasks

Use non-OpenAI models through OpenCode for bounded work with clear inputs and
observable results. Batch related operations into a useful task. A trivial
command can stay with the primary model when dispatch adds more work than it saves.

These are initial experiment choices to evaluate on scoped tasks.

| Task | Preferred candidate | Required result and boundary |
| --- | --- | --- |
| Git inspection | `opencode/glm-5.3-flash-free`, `low` | Branch/base, status, scoped diff, and conflicts. Read-only. |
| Shell operations | `opencode/glm-5.3-flash-free`, `high` | Bounded commands, exit status, output, and resulting local state. Follow existing project and action permissions. |
| Test execution | `opencode/deepseek-v4.1-flash-free`, `high` | Run the agreed checks on the pinned candidate. Return exact commands, results, failure evidence, and resource conflicts. |
| Screenshot inspection | `opencode/nemotron-3.5-super-vl-free`, `medium` | Inspect actual images at named viewports/states. Report visible defects with image paths and locations. |

Confirm each model and setting against the live catalog before dispatch.
Discovery, setting names, and unavailable-model handling follow
[Orchestration](orchestration.md) and the matching runtime adapter.
Report unavailable required workers under those rules.

For screenshot work, verify image input and access to the actual screenshot.
Verify browser or capture tools separately if capture is delegated. The browser
operator may capture images for another model to inspect. A model's vision
support alone does not establish browser access. Follow the runtime's browser rules.

Worker briefs permit only the actions needed for the task. Git inspection leaves
the index, checkout, refs, and remote unchanged, including no staging or stashing.
Any Git writes require explicit authorization for the action and its delegation.
Test runners execute checks; OpenAI owns changes to test design and application
code. Keep shared file and test-resource ownership with the coordinator.

## Council model preferences

| Role | Initial model preference | Settings |
| --- | --- | --- |
| OpenAI plan owner | The user's selected OpenAI model | Inherit the parent |
| Fresh OpenAI code reviewer | The user's selected OpenAI model | Inherit the parent |
| Technical planning challenger or GLM code-review seat | `opencode/glm-5.3-flash-free` | OpenCode variant `high` |
| Scope planning challenger or DeepSeek code-review seat | `opencode/deepseek-v4.1-flash-free` | OpenCode variant `high` |

The [Planning council](planning-council.md) and [Review council](council.md) own
their membership, independence, readiness, and reports. Keep model preferences
in this file when adapting the package for another installation.

## Evaluate the experiment

Record the actual provider/model/variant, task, candidate, useful results,
verification, elapsed time or usage when available, and required rework. Judge
support models by observed results. Change role preferences only from that
evidence or user direction; keep the OpenAI primary and permissions intact.
