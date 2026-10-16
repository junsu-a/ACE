# ACE — Agent Continuity Engine

> Sessions are temporary. Project knowledge is persistent.
>
> Agents come and go. Your project stays on course.

ACE is a local-first, human-centered control plane for AI-assisted software development. Working repository name: `ace-control-plane`; product name is provisional.

Developers working across coding sessions lose track of task progress, decisions, constraints, and where to resume. ACE aims to preserve project knowledge across those sessions and make actual progress understandable through inspectable evidence.

Its core value is continuity: understand what happened, what changed, what remains, what needs review, and how to continue without reconstructing every conversation. Agent claims must remain distinct from verified results.

## Initial focus

The initial environment is macOS, Git repositories, Codex Desktop, and Claude Desktop local Code sessions. Local-first storage and explicit authorization before sending sensitive data externally are requirements. Desktop integration feasibility is unproven.

The proposed MVP centers on one question: **“I returned to my project. Where did I leave off?”** Session discovery, task association, persistent knowledge, evidence-backed summaries, and resume context are candidates, not a finalized feature list. Starting as an Intelligent Observer is proposed; active enforcement and orchestration are future possibilities.

## Status

Product discovery and documentation only. No application, final architecture, dependencies, or feasibility experiment has been implemented. Python is the founder's preferred initial backend language; storage, interface, and integration choices remain open. A commercial product is a possible destination, not a validated business model.

## Documentation

| Document | Canonical responsibility |
| --- | --- |
| [Product vision](docs/PRODUCT_VISION.md) | Mission, users, concepts, outcomes, and non-goals |
| [Problem statement](docs/PROBLEM_STATEMENT.md) | Founder pain points and workflow scenarios |
| [Product principles](docs/PRODUCT_PRINCIPLES.md) | Invariants, privacy, human authority, evidence standards, and UX |
| [Requirements](docs/REQUIREMENTS.md) | Confirmed needs, MVP hypotheses, and future candidates |
| [MVP scope](docs/MVP_SCOPE.md) | Concrete first-release proposal and acceptance scenarios; pending founder review |
| [Decisions](docs/DECISIONS.md) | Status, authority, rationale, and decision history |
| [Research](docs/RESEARCH.md) | Sourced findings, integration options, and proposed experiment |
| [Open questions](docs/OPEN_QUESTIONS.md) | Unresolved risks and validation priorities |
| [Agent instructions](AGENTS.md) | Practical rules for future repository work |

Read the decisions and requirements before treating any proposed capability as a commitment.
