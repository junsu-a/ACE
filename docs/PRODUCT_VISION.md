# Product Vision

## Mission and philosophy

Enable developers to work across independent AI coding agents without losing project direction, critical knowledge, or human control. Make multiple sessions feel like one continuous, understandable project.

“Sessions are temporary. Project knowledge is persistent.”

“Agents come and go. Your project stays on course.”

ACE complements existing agents, Git, and editors. It should deliver immediate value through a simple experience, in the spirit of the founder's inspiration from focused utility products such as iLovePDF. First make something the founder wants to use; investigate a sustainable business after demonstrating recurring value.

## Target users

The first user is the founder: a software/platform engineer on macOS, using Codex Desktop and Claude Desktop local Code sessions across concurrent tasks and repositories. Sessions may be split to manage context windows and token consumption, or resumed after hours or days.

Other individual developers with similar workflows are a candidate audience, not a validated market. Teams are a possible later audience. Neither team collaboration nor SaaS infrastructure is an initial commitment.

## Founding problem and enduring direction

The founder's immediate pain comes from handling several work tasks at once, with each task spread across multiple Codex and Claude sessions. Every switch can require reconstructing what they were doing, where they stopped, which session to resume, what needs human review, and which critical invariants still apply. ACE should reduce that reconstruction effort while preserving project direction and human oversight.

This document preserves the full product vision so future sessions do not lose the original goal. Implementation will start small, with a focused slice of that vision. A smaller first release does not remove the other pillars or redefine ACE as only a session list, summary tool, or collection of memory files.

The proposed return-to-task experience is an entry point. Centralized Markdown, per-task records, automatic discovery, and desktop integrations are possible delivery approaches, not the product's purpose or accepted architecture. Their usefulness and feasibility can be tested incrementally without requiring the entire vision to be implemented first. Significant changes to the vision require an explicit founder decision.

## Product pillars

| Pillar | Intended outcome |
| --- | --- |
| Persistent project knowledge | Goals, constraints, decisions, tasks, progress, questions, and evidence outlive conversations. |
| Invariant preservation | Critical constraints stay visible; suspected conflicts can be reviewed. |
| Direction alignment | Changes to approved direction are deliberate and traceable. |
| Human oversight | Developers understand actual changes, evidence, uncertainty, and pending decisions. |
| Context continuity | Relevant context can be recovered without rereading every session. |

The binding standards for these pillars live in [Product principles](PRODUCT_PRINCIPLES.md); candidate capabilities live in [Requirements](REQUIREMENTS.md).

## Shared vocabulary

These are product concepts, not a database schema.

| Concept | Meaning |
| --- | --- |
| Project | Persistent software-development intent and knowledge, associated with repository work. Exact repository/worktree identity is unresolved. |
| Task | An objective that may span sessions and agents. Task state is independent of a session's lifecycle. |
| Session | A conversation or execution context in a coding tool. Ending a session does not establish task completion. |
| Hard invariant | A protected constraint requiring explicit authorized revision. |
| Architectural decision | A revisable choice with status, rationale, and authority. |
| Preference | A desired default that must not silently become a hard constraint. |
| Claim | A statement about progress or outcomes that may lack independent support. |
| Evidence | A source supporting a particular assertion within a stated scope. |
| Handoff/context package | Concise task-specific material for resuming work, with source references. |

## Desired experience

A developer returns to a project, selects a task, and understands its objective, recent changes, remaining work, blockers, review needs, and relevant sessions. They can inspect supporting sources and see missing or stale information. They can prepare context for continuing in the existing tool with little manual maintenance.

The proposed handoff contents are objective, relevant invariants and decisions, completed and remaining work, blockers, recommended next actions, and evidence references. Automatic delivery into another application is a separate future possibility.

## Success criteria

The central validation question is whether ACE reduces the effort needed to resume interrupted work while preserving accurate understanding. No performance targets or business outcomes have been validated.

Proposed evaluation, to calibrate with the founder:

- Compare time to a correct next action against the founder's current workflow on several interrupted tasks.
- Ask the developer to explain completed work, uncertainty, and review needs; compare their answer with underlying evidence.
- Record corrections to summaries and task associations, plus setup and maintenance time.
- Track whether the founder voluntarily returns to ACE over repeated interruptions.
- Later, test recurrence of the problem with other developers before investigating willingness to pay.

Faster resumption that produces false confidence is not success. Numerical acceptance thresholds remain [open](OPEN_QUESTIONS.md).

## Long-term possibilities and non-goals

An Intelligent Observer could evolve into an Active Guardian with context injection, deterministic checks, approval gates, and coordination. This evolution is optional and requires evidence and explicit decisions; see [decision status](DECISIONS.md).

Initial non-goals are replacing Codex, Claude, Git, an IDE, or a full project-management system; autonomous agent orchestration; automatic source changes; comprehensive policy enforcement; guaranteed detection of all conflicts; and mandatory cloud infrastructure. Monetization, team features, and a complete agent platform must not expand the first scope by default.
