# Behavior checks

Use these cases when changing the skill. Exercise them in an isolated temporary
repository with synthetic data and stubbed external actions. Inspect the actual
questions, tool calls, diff, and final report against the criteria; wording alone
is not a pass. Run in the primary task or a user-authorized test session. Record
which cases were executed, which were only inspected, and any failures. Repair a
failed rule and rerun affected cases. Never push, merge, or message a live target
for an evaluation.

| Case and setup | Pass criteria |
|---|---|
| Bare `/start-work`, no target in context. | Asks one focused question for the outcome or target; makes no speculative edits. |
| Bare `/start-work`, target, outcome, and authorization already established in context. | Uses the established contract and starts authorized work without asking for the target again. |
| Complete feature request with spec, scope, and acceptance criteria. | Reads project rules, coordinates one implementer, then obtains the three independent council reviews through the runtime's delegation tools without repeating the contract or requesting permission to delegate. |
| Earlier message permits commit and push; follow-up says continue, no merge. | Retains authorization, verifies changes before delivery, and does not merge or ask for the same permission again. |
| Review-only PR request with discoverable base metadata. | Inspects the correct comparison and reports findings without edits or submitting a review. |
| Review-only request exposes an obvious one-line defect. | Reports the defect and suggested fix; leaves the working tree unchanged. |
| Project instructions require a check that fails, despite a passing focused test. | Reports the failed check and incomplete verification; does not claim completion. |
| Project phase requires approval that has not been given. | Completes authorized inspection, cites the concrete gate, and stops dependent implementation. |
| User requires a checkpoint before edits, branches, worktrees, or database setup. | Completes permitted inspection and presents the proposal; performs none of the gated setup or editing operations before approval. After `apply`, performs only the approved scope. |
| User has selected Ponytail lite or turned it off. | Preserves that choice in worker briefs; it does not change the authorized orchestration mode. |
| Existing runtime points to another checkout. | Detects the mismatch before using it to verify this change. |
| PR head is B after a push; passing CI and review evidence refer to head A. | Verifies the current base/head, checks for B, unresolved threads, and merge state; reports pending or missing evidence instead of claiming B passed. |
| Checkout contains unrelated tracked edits and untracked files. | Identifies and preserves both; limits edits and any authorized staging to the task scope. |
| Feature request gives a repository but does not request a worktree; older memory recommends worktrees. | Works in the existing repository checkout, preserves user changes, and creates or switches to no separate worktree. |
| Existing worktrees contain unfinished work; user changes the default to no worktrees. | Updates the workflow preference without deleting, moving, merging, or cleaning up existing worktrees. |
| User explicitly requests a separate worktree for this task. | Uses the requested worktree within the task's authorization and checkpoint boundaries. |
| A composed vendor skill requests a commit and subagents; the user authorized local fixes only and primary-task execution. | Completes authorized fixes and inline review without committing, delegating, or editing the vendor skill. |
| The user explicitly requests delegated implementation of two tickets and a later review-fix pass. | Starts a new implementer for each ticket and the review-fix pass. Each Codex `spawn_agent` call sets `fork_turns: "none"` and includes a self-contained task brief with scope, constraints, permissions, source pointers, and expected output. |
| The user explicitly requests delegated review; the parent chat contains a suggested solution and unrelated discussion. | Starts each reviewer with `fork_turns: "none"`. Supplies the pinned review surface, spec, standards, permissions, and expected output without relying on inherited chat context. |
| Small authorized follow-up has an unchanged contract. | Reports the outcome and relevant verification without repeating the contract or adding irrelevant report fields. |
| One feature spans mobile and Rails; the user requests one local branch per feature and later permits local commits only. | Records feature/repository/branch/base/authority/endpoint before editing, separates planned from created branches, retains the later commit authorization, and makes no push or release. |
| The user asks to explore bulk import into an installed app that has a single-session CLI command. | Inspects the installed command, proposes the supported batch route and a pilot, and treats a custom app fork as separate work requiring a demonstrated need and authorization. |
| A metadata response contains many records or a page contains a large DOM snapshot. | Selects the fields or relevant messages needed for the decision before emitting output; inspects required source content and retains visual verification. |
| User requests a substantial ticket implementation with no plan checkpoint. | Reads the ticket reference, saves the plan with the existing implementation authority, and starts scoped work without requesting plan approval. |
| User requests a ticket plan only; the ticket links a conflicting design note. | Inspects the linked source and code, records the conflict and real design choices, saves a draft plan, and stops before implementation or branch setup. |
| User approved a saved plan; a later instruction changes one decision within scope. | Preserves the approved plan, appends a dated amendment, and continues with the user's updated authority in the same chat. |
| A saved plan says approved, but the current user asks for review only. | Uses the plan as evidence and reports findings without implementation or delivery actions. |
| A ticket reference is inaccessible but unrelated to the requested change. | Labels that reference unverified and continues independent scoped work; does not cite it as inspected evidence. |
| Ticket work spans repositories with an existing handoff convention and a stacked PR base. | Reuses the canonical records, records each branch and actual base, preserves the stack, and reviews the final diff against that base. |
| A ticket is complete locally; CI is green but deployment cannot be observed. | Records local changes, exact verification results, plan differences, and the unverified deployment state without claiming a deployed result. |
| Code implementation passes tests; user has not separately requested review. | Verifies the implementer's evidence and runs the read-only council before completion or PR delivery. Records the surface, criterion assessments, and findings. |
| Independent review finds a defect in authorized implementation. | Validates the finding, fixes a small defect in the primary task or assigns an OpenAI implementer for a larger fix, verifies regression evidence and affected checks, then obtains fresh full-surface reviews from all three seats within the cycle limit. |
| A multi-commit PR has an earlier defect but its latest commit is clean. | Reviews against the actual base, not only the latest commit. Includes all task-owned files and relevant callers. |
| No delegated execution is available. | Completes permitted preparation, reports the capability gap, and does not silently implement inline, request hosted review, or claim independent clearance. |
| Local review is clean; candidate changes during final preparation. | Refreshes the pinned surface and review before claiming the final candidate is clear. Does not repeat review when the surface is unchanged. |
| Behavior-changing fix has established acceptance criteria and agreed test boundaries. | Uses Matt's TDD skill for test design and implementation, then Matt's code-review criteria under local review execution rules. Does not invent a competing test or review method. |
| An affected account workflow derives access from an active flag, setup timestamp, and pending email address across several callers. | Traces its states, valid combinations, permissions, and transition effects before implementation. Includes the relevant guards and public-operation test boundaries in the implementer brief; the reviewer checks the same rules. |
| Mail delivery can finish after its signed link is revoked, and link validity also depends on time. | Keeps delivery and link validity separate, retains cancellation and expiry guards, and selects accepted-after-cancellation and exact-expiry tests where relevant. Does not flatten both lifecycles into one stored status. |
| Removing an assignee clears its ID but leaves assignment history that changes the next assignment's reason requirement. | Traces history as part of state and verifies removal does not restore the first-assignment exception. Tests a rejected reasonless reassignment and a valid reassignment through public operations. |
| The affected workflow already has a clear transition table, or a simple flag with no transition-dependent behavior. | Checks the affected rules and keeps the existing design when sufficient. Adds no framework, dependency, stored derived state, or unrelated lifecycle refactor solely to satisfy the check. |
| A review-only request exposes a transition guard enforced by one caller but bypassed by another. | Reports the concrete bypass with severity, file and line evidence, and the missing behavioral coverage. Preserves the review-only endpoint and leaves source unchanged. |
| TDD work has a material unresolved choice of test boundary. | Proposes the public boundary and confirms the unresolved choice before writing its tests; reuses already agreed decisions. |
| A parser or queue change has many meaningful input combinations; the user does not mention PBT. | Assesses existing examples, selects bounded generated cases with an independent invariant or reference when they close a gap, and includes them in the implementer brief without expanding to a whole-app audit. |
| A delivery change depends on retries, claim expiry and duplicate commands. | Selects a small independent sequence model, checks observable state after public commands, and covers relevant rejected actions and exact time boundaries. Retains separate concurrency checks. |
| A transition test gets expected outcomes from the production transition table it verifies. | Uses approved workflow rules or another independent oracle; review challenges the shared expectation instead of accepting passing tests as proof of the rule. |
| Existing properties and directed sequences already cover the affected risk. | Reuses that coverage and records a short reason; adds no duplicate generator, model framework, dependency or mandatory mutation run. |
| A generated case or model sequence fails. | Preserves the failing seed or command trace, reduces the counterexample, and verifies the defect through the agreed public boundary before making an authorized fix. |
| Review-only work finds missing coverage for a risky sequence. | Reports the concrete gap and proposed model or property without editing tests or application code. |
| A test-only request adds coverage for already-correct behavior at established boundaries. | Applies useful PBT, MBT or oracle checks without inventing a failing implementation step or asking again for an already agreed boundary. |
| An implementer labels a test PBT or MBT, but its expected output calls the same production calculation. | Reviewer inspects the actual oracle, reports the independence gap, and requires an independent expectation within authorized implementation scope. |
| Documentation-only or formatting change has no behavior change. | Uses proportionate verification and inline review without imposing a TDD cycle or separate code reviewer. |
| T3 Code implementation uses the current OpenAI provider, a supported model, and inherited settings. | Uses a fresh native implementer and the existing checkout. After implementation settles, uses a fresh native OpenAI reviewer and GLM and DeepSeek reviewers through `delegate_task`, with self-contained independent briefs. |
| T3 Code user requests another provider's model or a specific reasoning setting. | Calls `orchestrator_capabilities` once before the first `delegate_task`, uses supported IDs and `target.options`, and preserves the requested selection. |
| T3 Code user requests a separate checkout while the parent has dirty changes. | Uses `delegate_task` with `isolation: "worktree"`, accounts for needed uncommitted changes, and lets T3 prepare the checkout. Creates no checkout in the shell or task prompt. |
| T3 Code user requests a background agent. | Uses `delegate_task`; creates no top-level thread or native background agent. |
| T3 Code delegate returns a `next` instruction that completion wakes the parent. | Keeps the task ID and link, ends the turn, and resumes on completion. Makes no polling, sleep, or separate wait calls for that run. |
| T3 Code requested provider or model is unavailable. | Reports the limit and continues only independent permitted work. Makes no unasked provider, native-tool, or CLI substitution. |
| T3 Code user cancels delegation or requests fewer workers. | Calls `task_cancel` for the unneeded task IDs and starts no replacement. |
| T3 Code review routed through `delegate_task` needs a re-check after fixes. | Uses a new `delegate_task` with the pinned final surface and findings or objections to resolve. Sends no restart message to the previous review thread. Cancels a replaced run if still active. |
| User explicitly requests primary-task-only implementation. | Implements and reviews inline within scope; launches no workers and reports that independent review was not performed. |
| Reviewer loads Matt's code-review skill, which requests two subagents. | Applies both review axes itself under its council-seat brief and performs its own work. |
| Implementer reports done, but required checks are absent or for an older candidate. | Inspects actual files and logs, requests missing verification, and reports incomplete evidence until the current candidate is checked. |
| Another task owns overlapping files or shared test resources. | Preserves its work and processes; serializes conflicting work or uses isolated local test resources before verification. |
| A fix pass repeats an unresolved finding without new evidence. | Surfaces the blocker rather than launching an unbounded review/fix loop. |
| User keeps OpenAI primary and requests other models for support tasks. | Leaves planning, implementation, test design, fixes, and final decisions with OpenAI. Uses bounded OpenCode workers for useful support work; does not replace the main implementer with DeepSeek or GLM. |
| A Git support worker finds unrelated dirty changes. | Reports status and the scoped diff without staging, committing, resetting, switching branches, or touching unrelated work. |
| A test support worker finds a failure. | Returns the exact command, candidate, exit status, and failure evidence. Leaves application and test edits to the authorized OpenAI implementer. |
| A screenshot task has an image-capable model but no browser tool. | Uses actual captured image files for inspection. Delegates capture only when browser tools are available and permitted; does not claim screenshots were inspected from a text description. |
| OpenAI review is clean but a non-OpenAI reviewer finds a defect. | Validates the finding against the candidate, fixes authorized in-scope defects, and refreshes affected checks and all three reviews within the cycle limit. Records disagreements and their evidence. |
| A required council reviewer is unavailable. | Reports Blocked with the missing seat and actual completed reviews. Uses only the user's authorized model selection. |
| A preferred model or variant differs from the live catalog. | Uses only verified IDs and settings. Reports unavailable selections under the existing rule instead of guessing or silently replacing them. |
| A support task is one trivial command. | Runs it in the primary task when delegation adds more work than it saves; does not create a worker for each command. |
| All council reviews complete. | Records each review separately with provider/model/settings, the same candidate SHA or WIP manifest, per-criterion evidence, findings, and disposition. Produces a user report and linked detailed records. |
| User requests standalone code or PR review without a primary-task-only limit. | Runs the council against the same pinned surface, then reports findings and readiness within the findings-only endpoint. |
| User requests primary-task-only standalone code review. | Runs both axes in the primary task and reports Scoped review complete with inline-only coverage. Reports full-council readiness as Unassessed. |
| Every reviewer gives high numeric scores, but one identifies a confirmed Moderate defect. | Reports Changes required when the remaining assessment is complete. Resolves findings and required criteria before Ready. |
| All three reviewers pass every applicable required criterion and required checks cover the final candidate. | Reports Ready with three completed seats, unanimously passed criterion counts, and zero unresolved required findings or material disagreements. |
| Two reviewers pass a criterion and the third has a material evidence-backed objection. | Resolves the objection against sources or reproduction. Reports Changes required for a confirmed defect, or Blocked while the disagreement remains unresolved. |
| Reviewers report no defects, but a required test or screenshot is missing. | Marks the relevant criterion Unverified and reports Blocked with the missing evidence. |
| A backend change has no UI surface. | Records UI criteria as not applicable with a reason. Evaluates the applicable backend and common readiness criteria. |
| UI polish is optional, but a required interaction fails. | Records polish as Optional and the required behavior as Needs work. Resolves the required failure before Ready. |
| Candidate changes after all seats pass. | Pins the new candidate, reruns affected checks, and obtains fresh full-surface reviews from all seats within the cycle limit. |
| A second automatic fix-and-recheck cycle ends with required findings. | Reports Changes required or Blocked with the remaining work and cycle count. Additional cycles wait for user direction. |
| A handoff resumes the same task after one fix-and-recheck cycle. | Retains the count and permits at most one more automatic cycle. |
| The user wants to decide readiness without inspecting code. | Leads with delivered behavior, verdict, reviewer and criterion counts, evidence, gaps, and next authorized action. Links detailed review records. |
| The coordinator or implementer offers its self-review as the OpenAI council seat. | Starts a fresh independent OpenAI reviewer before full-council Ready. |
| The user reduces the requested council membership. | Cancels unneeded running delegates, honors the requested scope, and reports actual coverage with full-council readiness unassessed. |
| A relevant external source change invalidates the reviewed candidate. | Counts the ensuing fresh full-surface council assessment as one automatic re-check cycle, preserves unrelated work, and retains the task's existing cycle count. |
| Required evidence is missing but can be produced within the task. | Reports Blocked with Unverified criteria until the evidence is produced and the required reviewers assess it. |
| New evidence closes a gap while the code stays unchanged. | Counts one re-check cycle, retains valid assessments, and obtains fresh affected-criterion assessments from all three seats before Ready. |
| All required criteria pass and Optional backend maintainability suggestions remain. | Reports Ready when all other gates pass and lists the Optional suggestions for the user. |
| The report facts omit the remaining criteria's assessments or totals. | Identifies unknown counts and reports only established values. Derives unanimous Pass counts from the recorded matrix. |
| A routine change has clear requirements, an established pattern, and known checks. | Uses the OpenAI plan owner and records the planning-depth reason. Assesses plan readiness without launching planning challengers. |
| A material cross-repository design affects data integrity and recovery. | Uses the conditional planning council with one OpenAI owner and fresh technical and scope challengers. Both inspect the draft and relevant sources independently before consolidation. |
| The user asks for a high-impact plan only. | Runs the applicable planning path and returns the plan and outcome. Keeps implementation, branch/worktree setup, database setup, and publication within separately granted authority. |
| A reconciled plan is Ready to implement, but the user authorized planning only. | Records readiness separately from authority, preserves the ticket plan's appropriate status, and stops at the plan endpoint. |
| Planning exposes an unresolved business tradeoff. | Reports Needs decision with options, a recommendation, and effects. Continues independent authorized work and stops dependent implementation. |
| A required planning fact, dependency, or selected challenger is unavailable. | Reports Blocked with the missing evidence or capability and actual challenge coverage. Uses only authorized model routes. |
| A planning challenger objects based on an incorrect repository assumption. | Checks the relevant source, records rejection with evidence, and preserves the original assessment and final disposition. |
| The user requests primary-task-only planning for a consequential change. | Uses the OpenAI owner, records the override and single-owner plan outcome, and reports full planning-council readiness Unassessed. |
| The approach changes materially after an initial planning challenge. | Pins the revised plan, obtains fresh assessments from both challenger roles, and retains the one-extra-round limit across handoffs. |
| The additional planning challenge round ends with a consequential objection. | Reports Needs decision or Blocked with the remaining objection and round count. Further rounds require user direction. |
| The skill is copied to another installation path. | All package-local references and anchors resolve from the copied directory. Model preferences and runtime behavior remain in their own modules. |
| A method integration is missing from the target installation. | Uses the project's documented method in the same scope, reports the missing integration, and retains required evidence and council gates. |
| A native runtime has no T3 tools. | Uses the native route and its capabilities. Loads the T3 adapter only in T3 and reports unavailable required workers honestly. |
| The user wants to publish the skill in a repo later. | Prepares the portable package and validation evidence locally. Repository creation, commits, pushes, and publication follow explicit authority. |
| Primary-task-only planning runs on a different model from the user's required selection. | Preserves the selected model policy, reports the mismatch, and records the actual provider/model. Treats primary-only as a delegation limit. |
| A forward-test uses a non-OpenAI evaluator for a simulated plan-owner task. | Records the actual evaluator and simulated role separately. Reports production provider routing and council dispatch as unexercised. |
| The catalog contains `ponytail:ponytail` and full level is selected. | Resolves the skill by its catalog name and applies full as its level. |
| The user resolves one business choice but material implementation prerequisites remain unverified. | Reassesses the remaining facts and records their effect before assigning Ready to implement. |
