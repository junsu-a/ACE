# MVP 1 — Task Continuity

**Status:** Proposed scope for founder review, refined around the founder's suggestion of a shared workspace folder containing repositories and root agent instructions. The suggestion is not yet recorded as final approval of every boundary below. This document does not authorize implementation.

## Promise

**Switch to an active task and understand where you left off, what needs review, and how to continue without rereading its sessions.**

The first user is the founder, handling several concurrent tasks across the repositories of one local workspace on macOS, using Codex Desktop and Claude Desktop local Code sessions. MVP 1 delivers a small slice of all five [vision pillars](PRODUCT_VISION.md); the full vision remains intact under D-009.

## Recommended boundary

Start with a workspace folder, root instructions, file-based continuity records, and explicit session bootstrap/handoff steps. Automatic desktop discovery, transcript ingestion, and application-controlled session launching/reopening would not be release dependencies. This is a proposed delivery boundary, not a final application architecture.

The user or an agent following the workflow supplies a handoff. ACE must never claim it observed session activity that was not supplied. Preparing context for an existing agent does not authorize ACE to call a remote model or send project data externally.

## Workspace model

Illustrative structure, to finalize during implementation planning:

```text
workspace/
  AGENTS.md                 shared instructions and context entry point
  .ace/
    PROJECT.md              shared intent; links to canonical constraints/decisions
    TASKS.md                short index of active tasks
    tasks/
      task-a.md             task state and session references
      task-b.md
    handoffs/
      task-a/               separate session handoffs for reconciliation
  repos/
    service-a/              independent Git repository
    service-b/              independent Git repository
```

Gather only repositories relevant to this workspace. Existing repository paths can be referenced instead of moved; setup must not relocate or clone repositories silently. A workspace root is a context boundary, not blanket authority to modify every repository. Each task names its allowed repository paths and applicable project/repository constraints. Do not create an enclosing Git repository or change existing repository instructions as an implicit setup step.

Use `AGENTS.md` as the proposed shared entry point (rather than introducing a second `AGENT.md`). Starting a session from the workspace root is a convenience, not proof the tool loaded it. The bootstrap instruction explicitly names the root instructions, selected task, applicable repository instructions, and working repository. The same explicit read workflow is intended for both tools; automatic loading and desktop root-folder behavior remain untested.

## Included

| ID | Capability | Minimum behavior |
| --- | --- | --- |
| M-01 | Workspace orientation | A concise workspace entry point identifies shared goals, invariants, accepted decisions, repositories, and active tasks. Existing canonical documents are referenced rather than duplicated. |
| M-02 | Task continuity records | Each task preserves its objective, last handoff, remaining work, blockers, review needs, next action, and session references independently of conversations. |
| M-03 | Cross-agent session references | A task can reference multiple Codex and Claude sessions using a human-recognizable title/locator and tool name; an ID or URL is optional. Users can correct associations. Manual opening is sufficient. |
| M-04 | Explicit handoff updates | The user or an instructed agent records a concise update with source references and time. Reported outcomes, observed changes, check results, and unknowns remain distinct. |
| M-05 | Human review visibility | Each task exposes unresolved decisions, claimed completion needing review, and relevant changes/evidence. User approval of a result remains separate from evidence that a check passed. |
| M-06 | Resume context | Prepare a concise, inspectable task context containing the objective, relevant constraints/decisions, known progress, remaining work, blockers, next action, and evidence/session references. Manual paste or an instruction to read the local record is sufficient. |

Shared project direction and task state have separate responsibilities. The entry point stays short; task details and evidence stay in their canonical locations. Exact filenames, UI, commands, schemas, and storage mechanics are deferred to implementation planning.

## Core workflow

1. Establish the workspace entry point using existing goals, invariants, accepted decisions, and selected repository paths.
2. Create or select a task and record its objective and allowed repositories. Add references to the sessions contributing to it.
3. Manually start or resume a Codex/Claude session with access to the selected workspace context and repository. Supply the explicit bootstrap instruction; starting directory alone is not the integration contract.
4. At a task switch or session end, request a short, separate session handoff covering changes, evidence, uncertainty, remaining work, and next action. The user or a designated session reconciles it into task state. The user may supply or correct it directly.
5. Return through the workspace entry point, select a task, inspect review needs and evidence, and use the context to continue in the selected tool.

No continuous monitoring or guaranteed agent compliance is implied. A missing handoff remains a visible coverage gap.

## Update and authority rules

- Agents may propose task-state updates; only explicitly authorized humans revise protected project invariants or accept changes to project direction. Proposed decisions appear as pending.
- Scope each handoff to its task and identified session. Preserve conflicting reports for review rather than silently choosing a winner.
- Do not let parallel agents overwrite shared task state without reconciliation. The initial workflow can serialize updates to a task; live collaborative editing and automatic merging are excluded. A changed base record requires rereading and reconciliation before replacement.
- Display the last recorded handoff time and source. Do not describe it as the latest session activity or current repository state without supporting evidence.
- Commits and diffs support claims about changes, not proof of correctness. Check results need their command/result and relevant revision or working-tree state; unknown or stale scope remains explicit.
- Local records follow the existing privacy rules. No raw-history collection, remote summarization, telemetry, source execution, or automatic commits are needed for this scope. User-controlled local files remain inspectable and removable; no hidden retained copies are part of the proposed MVP.

## Explicitly excluded from MVP 1

- Automatic session discovery, private transcript parsing, and historical backfill.
- Automatic task classification or summaries generated from full conversations.
- Deep-link guarantees, automatic desktop/CLI session launching, one-click application-controlled resume, and automatic context injection. Explicitly starting a session in the existing tool is included; a launcher is a separate potential convenience.
- Background watchers, automatic test execution, and agent orchestration.
- Semantic invariant detection, deterministic enforcement, approval gates, and action blocking. Constraints remain visible; suspected issues can be explicitly recorded for review.
- Accounts, cloud storage/sync, team collaboration, billing, and hosted infrastructure.

These exclusions limit the first delivery, not the product vision. Adding one requires a deliberate scope revision.

## Acceptance scenarios

The MVP is functionally ready for a personal pilot when:

1. One workspace has at least two repository references and three active tasks; one task references both a Codex and a Claude session. The founder can switch among tasks and recover each objective, allowed repositories, last known state, review needs, and next action from the continuity records.
2. A new session can continue a task using its prepared context without requiring the full previous conversation to be copied.
3. A supplied “done” claim without verification stays unverified. A check from before a subsequent change is not presented as verification of that later change.
4. A missing handoff and conflicting reports remain visible. Updating one task does not erase another task's state or silently change an accepted project decision.
5. Records survive closing sessions and reopening the project; the complete workflow works without a vendor history API or ACE making external network/model calls.

These scenarios are proposed acceptance criteria, not executed tests or evidence of feasibility. During the pilot, compare recovery time, correctness, and handoff/correction effort with the founder's normal workflow across repeated task switches. Agree on numeric targets before claiming a measured improvement; working features alone do not validate product value.

## Next step after scope acceptance

Record founder acceptance and reconcile [Requirements](REQUIREMENTS.md), [Decisions](DECISIONS.md), [Open questions](OPEN_QUESTIONS.md), and the earlier integration-first experiment recommendation in [Research](RESEARCH.md). Then prepare a minimal implementation plan. No application code or experiment begins as part of locking this scope.
