# Research

## Research status and limits

As of 2026-10-15, this session inspected the repository drafts and conducted a limited public-documentation review. Sources below were opened, not merely inferred from search snippets. No product was installed or benchmarked, no private session stores were inspected, no desktop integration was exercised, and no customer interviews or pricing research were performed. Public searches contained generic product/integration topics, not local source code or conversation contents.

Documented vendor capabilities are not tested ACE capabilities. Research does not establish comprehensive competitive coverage, stable support across versions, commercial integration rights, or market demand. Recheck sources and installed versions before implementation.

## Existing products and substitutes

| Product or substitute | Evidence reviewed | Relevance and remaining question |
| --- | --- | --- |
| Codex | Official App Server documentation describes thread listing and reading. | Native history and integration surfaces may cover part of the need. Cross-vendor task continuity and access to the founder's desktop sessions still need evaluation. [Source](https://learn.chatgpt.com/docs/app-server) |
| Claude Code in Desktop | Official desktop documentation describes local sessions; its hooks reference documents session metadata. | Evaluate native workflow before adding another tool. This does not establish a general external API for discovering all existing desktop sessions. [Desktop source](https://code.claude.com/docs/en/desktop), [hooks source](https://code.claude.com/docs/en/hooks) |
| Entire Checkpoints | A first-party announcement describes capturing agent context in Git and a view combining session logs and code diffs. | This overlaps with context-to-change traceability. Current agent coverage, local-only behavior, task semantics, and invariant handling were not evaluated. No claim of an ACE-exclusive feature gap is justified. [Announcement, 2026-02-14](https://entire.io/blog/entire-dispatch-0x0001) |
| Git plus manual notes/instruction files | Git's documentation describes comparisons of working tree, index, and committed trees. Notes can supply human-maintained intent. | Baseline for testing whether ACE saves enough effort to justify itself; no comparative user study has been run. [Git reference](https://git-scm.com/docs/git-diff) |

Candidate differentiation is persistent task-level intent, explicit uncertainty, and portable context across tools with low maintenance. That is a positioning hypothesis, not a proven competitive advantage. Native tools and adjacent products may already satisfy enough of the need.

## Integration findings and approaches

### R-01: Codex documented protocol — promising, untested

The official [App Server reference](https://learn.chatgpt.com/docs/app-server) documents initialization, `thread/list`, `thread/read`, and version-specific schema generation. This is a stronger research starting point than guessing private file formats.

**Unknown:** whether a separately launched client can read the intended existing desktop histories with the installed version, configuration, permissions, and storage scope. A protocol for client-owned conversations does not automatically establish access to every desktop conversation or live event. Cross-client concurrency, schema maturity, network behavior, and supported lifecycle are untested. Capabilities exposed inside the current Codex chat are not automatically available to a standalone ACE process.

### R-02: Claude local sessions and hooks — distinct feasibility questions

Official [desktop documentation](https://code.claude.com/docs/en/desktop) describes local execution and local/SSH plugin installation. The [hooks reference](https://code.claude.com/docs/en/hooks) documents hook inputs including `session_id`, `cwd`, and `transcript_path`, and command hooks receiving JSON via stdin.

**Unknown:** which events and history are accessible in the founder's actual desktop workflow. A documented transcript path is not a promise of a stable transcript schema or a full historical-discovery API. Future event collection through opt-in hooks and retrospective recovery of old sessions must be evaluated separately. Installing hooks changes application configuration and is not a read-only research action.

### R-03: Git evidence — useful, limited

The [Git diff reference](https://git-scm.com/docs/git-diff) documents comparisons between working tree, index, and trees. These are candidate sources for observed changes.

**Inference for ACE:** Git evidence needs a repository/worktree identity and an identified state; concurrent changes, untracked files, rewritten history, and stale checks complicate interpretation. A changed file cannot by itself prove an agent's authorship or the task's correctness. Follow the canonical [evidence standard](PRODUCT_PRINCIPLES.md).

### Options requiring validation

| Approach | Potential value | Limitation or validation gate |
| --- | --- | --- |
| Documented protocol/API | Structured access without interpreting private storage | Prove coverage of existing desktop sessions, permissions, and supported versions. |
| User-authorized export or manual import | A bounded fallback with explicit selection | Verify an actual supported export, or use a manually prepared excerpt; measure friction and incomplete coverage. |
| Opt-in local hooks/event capture | Capture future session identity and events | Verify desktop compatibility, permission boundaries, event loss, and configuration lifecycle. Does not prove historical recovery. |
| Local MCP knowledge/context access | Potential way for an agent to retrieve project context | Hypothesis only: requires client support and intentional tool use; not passive session discovery or guaranteed injection. |
| Private files or UI automation | Possible exploratory fallback | Fragile formats, permissions, coverage, and maintenance; not a selected contract or a basis for claiming reliable integration. |

Python is preferred, not selected as a final stack. SQLite, a local API, and a lightweight desktop/web interface are legacy candidates, not research conclusions. No storage engine, model provider, inference strategy, or UI shell has been chosen.

## Smallest meaningful technical feasibility experiment

**Proposal P-006, not performed.** Timebox: one short session, approximately two hours; this is an AI estimate, not a product performance target. Test evidence recovery before building an application.

**Question:** Can a bounded local read path recover enough information from existing desktop work to assemble a trustworthy resume packet?

1. Agree on one disposable Git project containing non-sensitive synthetic work, one task, two existing local sessions (one per target tool), and explicitly selected data. Record installed app/tool versions and the intended read scope. Do not use production histories.
2. Attempt the documented read path for each tool. Inspect only the selected sessions; record identity, project association, time, and accessible messages or outcome metadata. Do not start inference turns, resume work, install hooks, or alter agent state as a side effect. Confirm any chosen read operations' side effects and network behavior first.
3. If existing-history access is unsupported or unavailable, stop that access attempt and record the gap. Use a founder-selected excerpt or supported export only as a separately labeled manual fallback; do not call this successful automatic discovery.
4. Record the synthetic project's Git revision and working-tree state with read-only operations. Manually assemble a short local Markdown packet containing objective, relevant constraint, observed change, agent claim, evidence reference, remaining work, and candidate session to resume. No model call, UI, database, watcher, or automatic context injection is needed.
5. Include an unsupported “done” claim and a check recorded before a later change. Confirm the packet keeps the claim unverified and the check scoped to its original state. Have the founder inspect the packet against the selected sources.

**Proposed pass criteria:** For each tool, record whether a supported path recovered the selected session and correctly linked its project; all packet factual assertions have inspectable references; both deliberately misleading cases retain their uncertainty; and no sensitive data leaves the selected local scope. Measure time and manual corrections without declaring a productivity improvement from one task.

**Stop conditions:** Access requires undocumented broad collection, unexpected writes, unapproved outbound data, or unavailable permissions. Report the limitation rather than expanding scope. A manual packet may support testing the value proposition while leaving automatic integration feasibility failed or unresolved.

**Deliverable for a later session:** A local feasibility report with per-tool results, versions, operations, source references, coverage gaps, packet, and go/narrow/stop recommendation. If a tiny throwaway reader is necessary, agree on that bounded experiment scope first; no application architecture should follow automatically from it.

## Further research

- Validate supported desktop access and behavior across updates, archived sessions, multiple worktrees, and concurrent clients.
- Compare native workflows, Entire, and manual handoff notes on the same interrupted task before claiming differentiation.
- Evaluate local-only extraction/summarization options, accuracy, resource cost, and what value survives without a model.
- Verify distribution/integration terms from first-party material before shipping adapters; no legal conclusion has been drawn here.
- Conduct small discovery interviews after demonstrating personal utility; record counterexamples and willingness to maintain another tool.

The prioritized unresolved decisions and ownership are in [Open questions](OPEN_QUESTIONS.md).
