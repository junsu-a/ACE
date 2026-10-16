# Problem Statement

## Evidence boundary

The founder reports these recurring problems in their own workflow. This is first-person discovery evidence, not proof of market prevalence, measured productivity loss, or willingness to pay. The scenarios below illustrate that report; they are not observations from a user study.

## User pain

| Reported problem | Practical consequence |
| --- | --- |
| Sessions become difficult to associate with tasks. | The developer opens several conversations to find the relevant work. |
| Completed and unfinished work are hard to reconstruct. | Work is repeated, abandoned, or prematurely treated as finished. |
| Architectural decisions disappear into conversations. | Later sessions reconsider settled choices without knowing their rationale. |
| Constraints and decisions conflict across agents. | The human must reconcile incompatible changes and assumptions. |
| New sessions require repeated explanation. | Context rebuilding consumes attention and tokens. |
| Agent reports are difficult to check against actual changes. | Confidence in progress exceeds available evidence. |
| Switching tasks is mentally expensive. | Returning after an interruption requires reconstructing intent and state. |
| More autonomous work is harder to oversee. | Decisions, risks, and approval needs become less visible. |

## Realistic workflows

### Returning the following day

The founder leaves a task across two Codex sessions and one Claude session. One reports success; another contains an unresolved blocker. The developer returns the next day and must identify the latest relevant work, check the repository, and determine a safe next step.

The unmet need is an accurate account of task state, including uncertainty. A chronological list of conversations alone may not supply it.

### Moving between agents or context windows

A task starts in one tool, is split after the context grows, and continues in another. The new session receives an incomplete account of a compatibility decision. The developer repeats instructions and later discovers conflicting approaches.

The unmet need is portable project direction and relevant task context. Automatic context injection is one possible solution, not a prerequisite established by this scenario.

### Concurrent work in one repository

Two sessions work on different tasks and touch overlapping files, possibly in separate worktrees. A later diff contains both contributions, and a passing test result refers to an earlier revision. Timestamps alone cannot establish which session produced each change or whether the current state was tested.

The unmet need is reviewable evidence with explicit attribution limits, rather than a single inferred completion percentage.

## Problems versus solution hypotheses

| Need | Candidate solution | What remains unproven |
| --- | --- | --- |
| Find the relevant work. | Session discovery and task association | Access to desktop sessions; accuracy and correction effort |
| Preserve project direction. | Persistent goals, invariants, and decisions | Capture burden and whether agents consult them |
| Understand actual progress. | Summaries with evidence references | Summary accuracy and evidence sufficiency |
| Resume efficiently. | Concise context package | Relevance, completeness, and time saved |
| Notice drift. | Suspected invariant-conflict reporting | Useful precision and alert burden |

## Why a session-centric view may be insufficient

A task can outlive, span, or share sessions. Conversation order does not encode approved decisions, current repository state, or verification scope. Git records changes but does not by itself reconstruct the task objective or all unresolved discussion. These are reasons to test a task-centric continuity layer, not claims that existing products cannot solve the problem.

Current alternatives include reopening conversations, maintaining handoff notes or repository instructions, and inspecting Git manually. Their adequacy and the overhead of ACE must be compared through [research](RESEARCH.md). The intended audience and outcomes are defined in [Product vision](PRODUCT_VISION.md).
