# Review council

Use this council for code implementation and standalone code or PR reviews.
The coordinator owns code inspection and gives the user a readiness report for
assessing delivered behavior and remaining decisions. Documentation-only and
formatting-only work uses proportionate inline review unless council review is
requested. Explicit primary-task-only or reduced-reviewer instructions take
precedence. When the requested override review finishes, label it Scoped review
complete, list findings and actual coverage, and mark full-council readiness
Unassessed. Apply full-council Ready only to the standard membership.

## Membership and independence

Use three fresh read-only reviewers, one OpenAI seat and the GLM and DeepSeek
seats from [Model roles](models.md#council-model-preferences).

Keep the implementer and coordinator separate from all three reviewer seats.
Confirm live models and settings and follow [Orchestration](orchestration.md) for dispatch, availability,
concurrency limits, callbacks, and cancellation. Let implementation settle before
review. Reviewers may run concurrently within available capacity, with shared
test resources serialized. Each reviewer performs its own work.

Give every reviewer the same pinned full candidate, requirements, standards,
acceptance criteria, applicability decisions, and raw evidence. Use
[Local review rules](reviews.md) for the independent brief and review method.
Each reviewer applies both Standards and Spec and inspects every applicable
criterion below before reading other reviewers' reports. Preserve each original
report before reconciling findings.

## Readiness criteria

Set the required criteria and their applicability from the agreed task and
project rules before dispatch. Each reviewer may challenge applicability with
evidence. Record a reason for each criterion that is not applicable. An applicable
criterion with missing evidence stays Unverified.

| Criterion | Required evidence |
| --- | --- |
| Requirements | Each acceptance criterion mapped to inspected behavior or checks |
| Correctness | Relevant normal, failure, and boundary paths inspected |
| Regression protection | Existing callers and workflows traced, with meaningful regression coverage |
| Verification | Required commands and results tied to the exact candidate and environment |
| Security and data safety | Applicable actor permissions, sensitive data, synchronization, and state integrity checked |
| Maintainability | Project conventions followed and complexity proportionate to the change |

Add criteria for affected risks. UI work covers responsive layout, accessibility,
interaction states, and actual screenshots. APIs cover contracts, authorization,
validation, and errors. Migrations cover integrity, compatibility, recovery, and
reruns. Scripts cover command permissions, partial failures, exit status, and
repeatability. Select criteria from the affected behavior.

Each reviewer marks every applicable criterion Pass, Needs work, or Unverified,
with evidence and a short reason. Distinguish an observed failure from missing
evidence. Required failures and acceptance gaps remain Needs work. Optional
improvements in any work type may accompany Ready when all required criteria pass.

## Findings and verdict

Classify findings by consequence and retain their Standards or Spec axis.

| Severity | Meaning |
| --- | --- |
| Critical | Security exposure, data loss, or widespread failure |
| Major | Required behavior fails or a significant regression exists |
| Moderate | A concrete defect or acceptance gap requires correction |
| Optional | A deferrable improvement or polish suggestion |

The coordinator validates findings against requirements, code, or reproductions.
Record rejected findings with the supporting evidence. Resolve disagreements
through evidence and retain the reviewers' actual positions. Record a material
disagreement when reviewers make incompatible evidence-backed claims. Numeric
scores alone establish neither a criterion assessment nor a factual objection.
A remaining material objection prevents Ready. Apply one verdict to the final candidate.

- **Ready** requires all three completed independent reviews, every applicable
  required criterion marked Pass by every reviewer, required checks passing on
  that candidate, and zero unresolved Critical, Major, or Moderate findings or
  material disagreements.
- **Changes required** applies when the assessment is complete and a confirmed
  defect or observed required-criterion failure needs correction.
- **Blocked** applies whenever required evidence or assessment is missing,
  stale, or unavailable, even when it can be produced in the current task.
  It also applies when a required reviewer or material decision is unavailable or an
  applicability or factual disagreement remains unresolved. Report any confirmed
  defects alongside the blocker.

Blocked takes precedence when missing assessment prevents a complete verdict,
including when confirmed defects also need correction.
Continue authorized work to fill recoverable gaps before handback, within the
cycle limit. Report remaining gaps as Blocked.

Use criterion counts and findings by severity in the report. Keep each
reviewer's evidence visible in the detailed records.

## Fix and re-check

Fix confirmed in-scope defects only when implementation is authorized. The
OpenAI coordinator handles small fixes and assigns larger fixes to the OpenAI
implementer. Standalone review ends with findings and a verdict.

Allow an initial council review and at most two automatic re-check cycles for
the task. Every reassessment after the initial reports counts, including fixes,
relevant external candidate drift, new evidence, and applicability changes.
Before dispatch, record the reason and increment once for the round covering
all seats. Combine related updates into one round. Keep the count across turns
and handoffs. Stop earlier for repeated unresolved findings or capability failures.
At the limit, report Changes required or Blocked with remaining work.

After a candidate change, rerun affected checks and obtain fresh reviews of the
full final surface from all three seats. With unchanged code and new evidence
or applicability, preserve valid assessments and obtain fresh assessments of the
affected criteria from all three seats. Each seat must record its own updated
assessment before Ready. Coordinator validation prepares that evidence for review.
Apply the runtime's fresh-task rule to each delegated re-check. Additional cycles
require user direction. Apply [Contract and permissions](contract.md#permissions)
and [Delivery](delivery.md) to subsequent actions.

## Report

Give the user a short report with the following information.

- Verdict, delivered behavior, and acceptance-check results.
- Completed reviewer count and unanimously passed required-criterion count.
- Confirmed findings by severity, their disposition, and unresolved decisions.
- Required verification results, known gaps, and applicable visual evidence.
- Reviewed base/head or WIP manifest and the next authorized action.
- Links to the detailed council records.

Calculate counts from recorded criterion assessments. Identify unknown counts
explicitly and report only totals that the records establish.

Keep a local matrix with one row per criterion and one column per reviewer.
Each cell records the assessment and evidence. Save each review separately with
provider, model, settings, candidate identity, scope, findings, actual checks,
and disposition. Use the project's local handoff convention for these records.
Record unavailable seats and scope overrides explicitly. The user report must
contain enough evidence to assess readiness without opening the code diff.
