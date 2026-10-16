# Requirements

## Status vocabulary

- **Confirmed:** explicitly required by the founder. This establishes a product need or boundary, not that a particular delivery method is feasible or belongs in the MVP.
- **Hypothesis:** a candidate solution, scope, or success measure requiring validation and founder acceptance.
- **Future candidate:** a possible later capability with no delivery commitment.

The accepted choices and proposals are recorded in [Decisions](DECISIONS.md). Binding interpretations of privacy, evidence, and human authority live in [Product principles](PRODUCT_PRINCIPLES.md). No MVP feature set has been accepted.

The full [product vision](PRODUCT_VISION.md) remains the long-term direction. Implementation will start with a small slice; leaving a capability out of the first release does not discard its underlying product pillar. The current work preserves intent rather than finalizing an implementation plan (D-009).

## Confirmed functional needs

| ID | Requirement | Review criterion for a future design |
| --- | --- | --- |
| F-01 | Preserve project goals, invariants, decisions, tasks, progress, open questions, and evidence beyond sessions. | Ending or replacing a session does not erase the relevant project knowledge. |
| F-02 | Represent work around tasks that can span agents and sessions. | Task state is not equated with whether a session ended. |
| F-03 | Distinguish hard invariants, revisable decisions, and preferences. | Each type has explicit scope and cannot silently change category. |
| F-04 | Support human understanding of actual progress, remaining work, changes, risks, conflicts, and pending decisions. | A reviewer can identify known state and uncertainty without treating a completion claim as proof. |
| F-05 | Make important changes in project direction reviewable and traceable. | Proposed changes remain distinguishable from human-approved changes. |
| F-06 | Support resuming work with relevant project/task context. | The developer can determine a next action and supporting context; delivery mechanism remains open. |

## Confirmed non-functional requirements and boundaries

| ID | Requirement | Design-review implication |
| --- | --- | --- |
| N-01 | Local-first storage and privacy under I-01 | Sensitive collection and any outbound processing have explicit boundaries; cloud infrastructure is not mandatory. |
| N-02 | Human authority and evidence standards under I-02–I-05 | Sources, verification scope, unknowns, and approval origin remain inspectable. |
| N-03 | Initial environment: macOS, Git, Codex Desktop, Claude Desktop local Code sessions | Verify actual installed surfaces; CLI or SDK support alone does not prove desktop access. |
| N-04 | Vendor independence and inspectability under I-06 | Do not make a proprietary conversation format the sole definition of project knowledge. |
| N-05 | Minimal manual administration and focused scope under I-07 | Compare capture/correction effort with time saved before adding automation. |
| N-06 | No assumed stable private APIs, session files, or deep links | Record contract status, coverage gaps, and fallback behavior for each integration. |

Latency targets, data-volume limits, offline behavior, retention periods, encryption mechanisms, accessibility acceptance criteria, packaging, and supported version ranges are not finalized. See [Open questions](OPEN_QUESTIONS.md).

## MVP hypotheses

A concrete [MVP 1 scope proposal](MVP_SCOPE.md) now explores a file-first workspace with shared root instructions, task records, and explicit session handoffs (P-007). It is pending founder review. The candidates below remain the broader hypothesis set; they are not all required by that proposal.

Proposed primary job: **“I returned to my project. Where did I leave off?”** These candidates must be tested and narrowed together; this table is not a release checklist.

| ID | Candidate | Validation needed |
| --- | --- | --- |
| H-01 | Discover relevant local Codex and Claude sessions. | Supported access, history coverage, project identity, and permissions; manual selection/import may be an acceptable fallback. |
| H-02 | Associate multiple sessions with a task. | Whether suggested associations are accurate and cheap to correct; allow unresolved associations rather than forced guesses. |
| H-03 | Maintain a small persistent project-knowledge record. | Which fields users actually need and whether capture can avoid duplicate maintenance. |
| H-04 | Summarize cross-session progress with Git references and explicit uncertainty. | Accuracy, evidence relevance, uncommitted-change coverage, and conflicting contributions. |
| H-05 | Present a concise return-to-task view. | Whether users correctly identify next steps and review needs faster than their current workflow. |
| H-06 | Prepare a task-specific context package and identify relevant sessions. | Context usefulness, length, stale references, and whether manual copy/open is sufficient. Automatic resume is not assumed. |

Proposed evaluation cases: an unsupported completion claim remains unverified; a stale check is labeled as applying to earlier state; ambiguous contributions stay unattributed; unavailable history produces an explicit coverage gap; a user can correct a mistaken task association. These are AI-recommended validation cases, not evidence of implemented behavior.

## Future candidates

- Suspected semantic invariant conflicts and direction-drift alerts.
- Deterministic checks for machine-verifiable project constraints.
- Automatic context injection and application-controlled resumption.
- Approval gates, active prevention, and agent coordination.
- Team collaboration, optional synchronization, and commercial hosting.

No future candidate is authorized merely by inclusion here. A read-only observer cannot guarantee prevention; an active guardian would need separately validated control over the relevant execution paths.

## Implementation entry conditions

Before application implementation, resolve the highest-priority [questions](OPEN_QUESTIONS.md), validate a bounded integration path, agree on the smallest useful return-to-task workflow, and record the founder's MVP decision. These are AI recommendations for the next phase, not a new architecture mandate. The current session authorizes documentation only.
