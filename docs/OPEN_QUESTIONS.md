# Open Questions

All questions below are unresolved. Priorities and suggested validation are AI recommendations. The founder owns product and scope acceptance; a future implementer can gather technical evidence but cannot silently approve a change in direction.

## Five largest unresolved risks

| Priority / ID | Risk and consequence | Evidence needed / next action | Decision owner |
| --- | --- | --- | --- |
| 1 / Q-01 | Existing desktop-session access may be incomplete or fragile. Core discovery could depend on unsupported storage or require a different workflow. | Run the bounded [feasibility experiment](RESEARCH.md); distinguish existing-history access from future capture and per-tool coverage. Accept a manual fallback or narrow scope if needed. | Founder, informed by technical evidence |
| 2 / Q-02 | Progress summaries may imply correctness or attribution that evidence cannot support, especially with concurrent edits and stale checks. | Test unsupported claims, conflicting sessions, dirty worktrees, and outdated verification against the [evidence standard](PRODUCT_PRINCIPLES.md). Decide what task status can honestly mean. | Founder, informed by evidence review |
| 3 / Q-03 | Collecting histories creates another sensitive-data store; extraction, telemetry, or model calls could break privacy. | Define collection consent, allowed paths, derived-data handling, network boundaries, retention/deletion, and a threat model before an adapter or inference design. | Founder, with security review before implementation |
| 4 / Q-04 | Capturing and correcting project knowledge may cost more attention than ACE saves. | Compare setup, association corrections, and repeated resume time against existing notes/native workflows. Decide the minimum manual input and fallback acceptable to the founder. | Founder as first user |
| 5 / Q-05 | The problem may not justify a separate product, or differentiation may be weak. | Demonstrate recurring personal use, compare alternatives including Entire, then interview similar developers. Test willingness to adopt before willingness to pay. | Founder |

## Product and UX questions

- **Q-06 — Before MVP scope acceptance:** What is the minimum useful return-to-task output? Is a local Markdown packet enough to validate value before any interface?
- **Q-07 — Before MVP scope acceptance:** Must both target tools support automatic history discovery at launch, or is one integration plus explicit manual import useful?
- **Q-08 — Before task association design:** Can one session contribute to several tasks? How should users split, merge, correct, or leave associations unresolved? What identifies a project across clones, worktrees, renames, or repositories?
- **Q-09 — Before knowledge capture design:** Which goals, decisions, and invariants are entered manually, suggested by an agent, or extracted? Who confirms an inferred constraint and resolves contradictory sources?
- **Q-10 — Before summary design:** What belongs in a context package, how concise should it be, and how are relevant sources selected? Is identifying a session with manual navigation sufficient?
- **Q-11 — Before pilot evaluation:** What baseline tasks, repeat-use period, accuracy threshold, maintenance budget, and resume-time improvement define success? No numeric targets are accepted yet.

## Technical feasibility questions

- **Q-12 — Before choosing an integration:** Which public interfaces cover the actual installed Codex Desktop and Claude Desktop local Code workflows? What permissions, authentication, side effects, and version constraints apply? Is historical reading supported independently of starting work?
- **Q-13 — Before persistence design:** What should ACE retain: references, excerpts, raw transcripts, derived facts, or snapshots? How should missing sources, schema migrations, corruption, backups, and rewritten history be handled?
- **Q-14 — Before automated summaries:** Can useful extraction work locally within acceptable latency and hardware limits? Is a deterministic/manual first workflow enough? What happens with no model or network?
- **Q-15 — Before choosing the stack:** Does Python fit the validated integration and macOS packaging constraints? What storage and UI are actually needed? SQLite, a local API, and a desktop/web shell remain candidates only.
- **Q-16 — Before automated evidence collection:** How will untracked files, partial commits, overlapping tasks, rebases, and concurrent changes be represented? How is the state checked by a test identified without claiming that a later state was verified?
- **Q-17 — Before background operation:** What freshness, collection intervals, data volumes, CPU/memory use, and supported app versions are acceptable? How should version changes and coverage loss appear to users?

## Privacy and security questions

- **Q-18 — Before data collection:** What explicit selection/consent flow limits repository and session access? How will secrets, personal information, cross-project leakage, and permissions be handled without assuming redaction is infallible?
- **Q-19 — Before persistence:** What retention, deletion, export, backup, and encryption behavior is required? Do search indexes, derived summaries, and recovery copies follow deletion? Can project data accidentally enter Git or synced folders?
- **Q-20 — Before any outbound processing:** Is optional remote inference acceptable at all? If so, what data/purpose disclosure and authorization are required? What local behavior remains available when authorization is absent or revoked? Telemetry and crash reports need the same scrutiny.
- **Q-21 — Before import or action features:** How are malicious instructions in conversations/repositories separated from policy, and how are source tampering and forged test results represented? No imported “approval” should authorize an action.
- **Q-22 — Before an Active Guardian proposal:** Which execution paths can actually be controlled, and which bypass enforcement? What does an approval authorize, how long is it valid, and how are changed inputs and policy revisions handled?

## Market and long-term questions

- **Q-23 — After personal utility:** Which developer segment experiences this pain often enough to adopt another tool? Is portable intent, evidence review, or context recovery the strongest reason?
- **Q-24 — Before positioning claims:** What do native tools and competing products already do well? Is ACE meaningfully better than disciplined notes plus Git, or better as an integration into an existing tool?
- **Q-25 — Before commercial commitments:** Would users pay for a local product, optional services, or team capabilities? What support costs and integration terms affect sustainability? No SaaS or subscription model is selected.

## Recommended next-session order

1. Read [Decisions](DECISIONS.md) and [Requirements](REQUIREMENTS.md); resolve the experiment's scope and selected synthetic inputs with the founder.
2. If authorized, perform only the bounded research experiment, recording unsupported capabilities as gaps rather than expanding access.
3. Review the packet's usefulness and per-tool evidence with the founder. Narrow or reject the MVP hypothesis if the result warrants it.
4. Record accepted scope and unresolved risks, then propose the smallest implementation plan. Select architecture only after these findings; do not automatically begin the application.
