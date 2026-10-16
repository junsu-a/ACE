# Product Decision Log

Reconciled on 2026-10-15 against the founder's discovery brief and existing repository drafts. Accepted means explicitly directed by the founder, not validated in the market or implemented. AI recommendations remain Proposed until the founder accepts them.

Statuses: **Proposed / Accepted / Superseded**. Keep superseded entries and link replacements; do not silently rewrite the history. The canonical meaning of product invariants is in [Product principles](PRODUCT_PRINCIPLES.md).

## Accepted founder decisions

| ID | Decision | Status / authority | Context and rationale | Consequence |
| --- | --- | --- | --- | --- |
| D-001 | Solve a personally experienced problem first. | Accepted / Founder, explicit brief | Repeated context reconstruction is painful in the founder's own workflow. | Validate personal utility before monetization; commercial SaaS is optional. |
| D-002 | Prioritize persistent project continuity. | Accepted / Founder, explicit brief | Project intent must survive individual sessions. | Preserve the five product pillars in [Vision](PRODUCT_VISION.md). |
| D-003 | Support human understanding and review. | Accepted / Founder, explicit brief | Agent reports alone do not establish outcomes. | Preserve authority, evidence, and uncertainty under I-02–I-05. |
| D-004 | Target local desktop workflows first. | Accepted / Founder, explicit brief | macOS, Git, Codex Desktop, and Claude local Code sessions reflect the initial workflow. | Validate those environments; do not substitute CLI support as proof. |
| D-005 | Require local-first privacy. | Accepted / Founder, explicit brief | Project data can be sensitive. | Apply I-01 throughout; no unauthorized external data processing. |
| D-006 | Organize around tasks and remain vendor-independent. | Accepted / Founder, explicit principles | A task may span multiple tools and sessions. | Session state cannot define task completion or own persistent project knowledge. |
| D-007 | Keep this phase to discovery and documentation. | Accepted / Founder, explicit working rules | The product needs a durable foundation before code. | No application or experiment implementation, final stack selection, or unnecessary dependencies in this phase. Commits and pushes require founder approval. |
| D-008 | Complement existing developer tools with focused scope. | Accepted / Founder, explicit brief | ACE should reduce effort in an existing workflow. | No replacement IDE, Git, agent, or full orchestration platform in the first iteration. |
| D-009 | Preserve the full vision; start implementation small. | Accepted / Founder, explicit clarification, 2026-10-15 | The current goal is to document the original intent so it survives future sessions. The founding pain is switching among concurrent tasks, each spanning multiple Codex/Claude sessions, while retaining context, invariants, and human review. | Keep all five pillars in the vision. Treat a small first implementation as a delivery slice; do not silently replace the vision with an MVP hypothesis or an integration/storage choice. |

## Proposals and preferences

### P-001: Start with an Intelligent Observer

- **Status:** Proposed.
- **Origin:** Founder proposal, reiterated in existing drafts; not yet accepted as a final strategy.
- **Context/rationale:** Continuity and evidence may deliver value before ACE can control execution.
- **Alternatives:** Active Guardian first; a narrower manual handoff utility.
- **Consequences:** Observation cannot guarantee prevention. Design should leave room for later control without building it now.
- **Validation:** Useful return-to-task experience and a maintainable observation path.

### P-002: Initial technical stack

- **Status:** Proposed; no architecture selected.
- **Origin:** Founder preference for Python as initial backend. SQLite, local API, and lightweight desktop/web UI appeared as candidate stack elements in the pre-existing draft; their author and approval are unverified.
- **Context/rationale:** Prefer a simple local implementation if it fits validated integrations and UX.
- **Alternatives:** Other storage, process, and interface arrangements after feasibility work.
- **Consequences:** No dependencies, framework, database, or application shell are authorized by this proposal.
- **Validation:** Integration constraints and an accepted MVP must inform the choice.

### P-003: Task-centric organization — legacy proposal resolved

- **Status:** Superseded by D-006.
- **Origin:** Pre-existing draft labeled this Proposed; the founder's current brief explicitly identifies task-centric design as a principle.
- **Rationale/consequence:** Record the correction without leaving a contradictory open proposal. Association automation remains H-02, not an accepted implementation.

### P-004: Minimize cloud dependencies — legacy proposal resolved

- **Status:** Superseded by D-005 and I-01.
- **Origin:** Pre-existing draft labeled this Proposed; the founder's brief explicitly requires local-first privacy.
- **Rationale/consequence:** Privacy is required, while optional authorized remote features remain undecided.

### P-005: Return-to-project MVP

- **Status:** Proposed.
- **Origin:** Founder MVP hypothesis.
- **Context/rationale:** Answer “Where did I leave off?” exceptionally well before expanding scope.
- **Alternatives:** Session inventory only; manual context preparation; invariant monitoring first.
- **Consequences:** Discovery, association, summaries, Git evidence, and handoffs remain candidates in [Requirements](REQUIREMENTS.md), not a promised bundle.
- **Validation:** Faster, accurate resumption with less maintenance than current practice.

### P-006: Run a bounded evidence-recovery feasibility experiment next

- **Status:** Proposed.
- **Origin:** AI recommendation from this documentation session.
- **Context/rationale:** Existing desktop-session access and trustworthy Git association are major uncertainties.
- **Alternatives:** Broader integration prototype; immediate UI implementation; continued interviews only.
- **Consequences:** Test one synthetic task with two sessions and a local evidence packet; no runtime architecture commitment.
- **Validation:** Use the bounded protocol and stop conditions in [Research](RESEARCH.md). The experiment has not been started.

### P-007: File-first workspace for MVP 1

- **Status:** Proposed; detailed scope pending founder review.
- **Origin:** Founder suggested a folder gathering relevant repositories with root agent instructions and sessions started from that context. AI elaborated the boundaries in [MVP scope](MVP_SCOPE.md).
- **Context/rationale:** Test task continuity with shared files and explicit handoffs while reducing dependence on vendor session interfaces.
- **Alternatives:** Integration-first observation under P-006; a single project context file; automatic session discovery as a release requirement.
- **Consequences:** Proposed MVP uses shared workspace instructions, task records, separate session handoffs, and manual bootstrap/navigation. Automatic launching, discovery, and transcript processing are excluded from the draft. Neither implementation nor a final technical stack is authorized.
- **Validation:** The acceptance scenarios in MVP scope include multiple tasks/repositories, both tools, evidence limitations, and interruption recovery. No validation has been performed.

## Future decision record template

Record ID/title, status, date, origin/authority, source of explicit acceptance, context, decision or proposal, rationale, alternatives, consequences, validation evidence, affected invariants/documents, and supersedes/superseded-by links. If origin or acceptance is unknown, say so. Record significant revisions and update affected canonical documents together.
