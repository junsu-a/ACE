# ACE — Agent Continuity Engine

> Agents come and go. Your project stays on course.

ACE is a local-first control plane for AI-assisted software
development.

It helps developers maintain project continuity, preserve
critical constraints, understand progress, and stay in control
while working across multiple AI coding agents and sessions.

## The Problem

AI coding tools are powerful, but their context is fragmented.

Developers frequently:
- Run multiple sessions across Codex and Claude.
- Split a single task across sessions to manage context usage.
- Work on several tasks concurrently.
- Forget which session contains the latest work.
- Repeat instructions, requirements, and decisions.
- Lose track of architectural constraints.
- Struggle to verify what agents actually accomplished.
- Spend time reconstructing context before resuming work.

The problem isn't a lack of capable agents.

It's a lack of continuity and oversight between them.

## The Vision

ACE provides a persistent project-level control plane
independent of individual AI sessions.

It aims to answer five questions:

1. What are we trying to accomplish?
2. What must never be violated?
3. What has actually been completed?
4. What requires my attention?
5. Where and how should I continue?

## Core Principles

- Sessions are temporary. Project knowledge is persistent.
- Project intent must survive context resets.
- Critical invariants must be explicit and reviewable.
- Agent claims are not equivalent to verified results.
- Humans retain authority over important decisions.
- Context switching should require minimal effort.
- Local-first privacy is a fundamental requirement.

## Initial Scope

- macOS
- Codex Desktop
- Claude Desktop (local Code sessions)
- Local session discovery
- Cross-session task tracking
- Persistent project knowledge
- Evidence-backed progress summaries
- Context recovery and handoffs

## Status

Discovery / Product Definition

No implementation has been finalized.
