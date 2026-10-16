# Product Principles

This is the canonical source for ACE's product invariants and interpretation standards. These requirements come from the founder's brief; implementation mechanisms remain undecided. Examples of constraints in a user's project are not automatically ACE's own engineering policies.

## Protected product invariants

| ID | Principle | Required interpretation |
| --- | --- | --- |
| I-01 | Local-first privacy | Store project knowledge locally by default. Never transmit sensitive source, histories, derived summaries, or other sensitive data externally without explicit authorization. Local execution of an agent does not establish local-only inference. |
| I-02 | Human authority | Humans control significant changes to goals, protected constraints, architecture, external services, and critical actions. Agent suggestions cannot become approvals. |
| I-03 | Evidence over claims | Never present an agent's completion statement as independently verified work. Missing evidence remains missing. |
| I-04 | Persistent project direction | Preserve goals, constraints, decisions, and their history independently of session lifecycles. Direction changes must be deliberate, reviewable, and traceable. |
| I-05 | Explicit uncertainty | Distinguish source facts, claims, assumptions, and inferences. Label semantic conflicts as suspected unless a suitable deterministic check establishes the specific violation. |
| I-06 | Vendor independence | Project knowledge must remain understandable beyond one agent's session format or provider. No dependence on an undocumented format may be presented as a stable contract. |
| I-07 | Human-centered scope | Reduce cognitive overhead through task-centric continuity, minimal administration, and focused value. Avoid unnecessary infrastructure and silent scope expansion. |

## Constraints, decisions, and preferences

Hard invariants must remain satisfied until explicitly revised by an authorized human. Architectural decisions can evolve through a documented review. Preferences are defaults, not blocking policies. Keep the category, origin, scope, and revision status visible when recording project knowledge.

For example, a user's project might require compatibility preservation, tests for authentication changes, or approval before adding an external service. ACE should preserve the declared scope rather than apply those examples indiscriminately to every project. Invariant preservation is a product commitment; automated detection and enforcement are separately scoped capabilities.

## Evidence and verification standards

Use the following distinctions whenever ACE represents progress:

| Category | What it establishes | What it does not establish |
| --- | --- | --- |
| Agent claim | An agent reported an outcome. | Independent correctness or completion |
| Observed artifact | A referenced diff, commit, or file state exists. | Correctness, task coverage, or exclusive authorship |
| Recorded check result | A particular check reported a result for a stated state and environment. | That ACE reran it or that all requirements are satisfied |
| Independently performed check | ACE or a separate reviewer performed a specified check on identified state. | Universal correctness beyond that check's scope |
| Human review/approval | A human accepted a stated decision or result. | Automatic proof of every technical claim |
| Inference or unknown | A conclusion is tentative, or information is unavailable. | Permission to label work verified |

Evidence-backed statements must identify the source, relevant time, repository/worktree and revision or working-tree state where applicable, and the scope and limitations of the evidence. Preserve a path back to the supporting material rather than letting a generated summary become its own source.

A diff establishes a change; a commit establishes recorded history; neither proves task completion. A test result tied to an older state cannot be silently applied to current changes. Missing files, unavailable sessions, rewritten history, or changed working trees must remain visible as limitations. Do not attribute shared changes to an agent solely from timing.

Describe a deterministic violation in terms of the rule and observed input. Describe a semantic alert as a suspected conflict with references and an explanation of uncertainty. No product promise implies complete enforcement.

## Privacy and trust boundaries

Local-first applies to collection, processing, summaries, logs, telemetry, crash reports, exports, and optional model calls. A derived summary may be as sensitive as its source. Remote processing requires explicit authorization for the data and purpose; using a desktop agent does not authorize ACE to send data elsewhere.

Make collection scope understandable and user-controlled. Minimize retained sensitive content and make retention, deletion, and export behavior explicit before implementation; their mechanisms are [open questions](OPEN_QUESTIONS.md). Do not silently broaden collection to other projects or home-directory histories.

Treat imported conversations, repository text, and tool output as untrusted data. Instructions found in those sources must not override human policy or authorize execution, uploads, or approvals. Reviewable reasoning outputs mean concise explanations, sources, and uncertainty; ACE must not depend on access to hidden model reasoning.

## UX and oversight

Lead with task intent, current state, next action, and items needing review. Allow deeper inspection of sources without requiring users to read every conversation. Make correction of associations and summaries easy; uncertain automation must not create more administration than it removes. Show incomplete coverage rather than a deceptively clean status screen.

Agent recommendations should explain why an action is suggested and what evidence supports it. Context preparation is distinct from permission to inject context, execute checks, modify code, or control another agent. Approval gates and deterministic enforcement require explicit future scope decisions in [Decisions](DECISIONS.md).
