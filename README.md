# RoboFleet Coordinator — Band of Agents Hackathon

> [!IMPORTANT]
> ### 🏆 GRAND PRIZE POOL: $10,000+ USD!
> **1st Place:** $3,500 USD Cash! Let's orchestrate a legendary multi-agent swarm to conquer the leaderboard! 🐝🚀


> Entry for the **Band of Agents Hackathon** (lablab.ai × Band). *"Build enterprise multi-agent systems with Band and Codeband."* Fully online · build **Jun 12–19, 2026** · **$9,500 prize pool.**

**Tagline:** Orchestrate a fleet of autonomous inspection and delivery robots — task allocation, coordination, and conflict resolution — with Band as the cross-agent collaboration layer.

## Community

Building this in the open — join the team chat on Discord: https://discord.gg/A3ZBBMFREs

## The hackathon

Most AI agents work alone, locked inside one framework or workflow. Enterprise work is collaborative. **Band** is a shared interaction layer where agents communicate, exchange structured context, coordinate actions, discover/recruit other agents, and work together **across frameworks**. The challenge: build a multi-agent system where **at least 3 agents collaborate through Band** across planning, execution, review, decision-making, or task handoff — with Band as the *central* collaboration layer, not a thin wrapper.

## Use case: multi-robot fleet coordination

Autonomous robot fleets — warehouse delivery bots, site inspection drones, last-mile AMRs — face exactly the coordination problem Band is built for:

- **Task allocation**: a new mission arrives (e.g. "inspect bay 7, then deliver to dock 3"). Which robot is closest? Which has the right sensor payload? Who is already overloaded?
- **Conflict resolution**: two robots converge on the same corridor. Which yields? Who re-routes?
- **Adaptive replanning**: a robot goes offline mid-task. Hand off to a peer without losing progress or context.

Each robot runs as an independent agent. Band provides the coordination layer — shared task state, structured context handoffs, cross-framework agent discovery, and escalation to a human operator when a conflict can't be resolved autonomously.

## Track & fit

Three tracks: Internal Enterprise Workflows · **Multi-Agent Software Development** (Codeband reference) · **Regulated & High-Stakes Workflows**. Our fit is **Track 3** — autonomous systems operating in physical environments where failures have real consequences, with meaningful human-in-the-loop escalation paths. Track 2 Codeband patterns also apply for the planning/simulation tooling.

## What we're building

A multi-robot fleet coordination system built on Band:

| Agent | Role |
|---|---|
| **Fleet Planner** | Receives incoming missions, scores available robots (proximity, capacity, current load), and emits allocation decisions through Band. |
| **Robot Agent ×N** | Represents one physical or simulated robot. Accepts tasks, reports status and position, requests re-routing help when blocked. |
| **Conflict Resolver** | Monitors shared spatial state in Band; detects contention (two robots on collision course, competing resource claims) and negotiates resolution. |
| **Human Operator (HITL)** | Escalation endpoint for unresolvable conflicts, safety-critical decisions, or mission priority overrides. Receives structured context from Band and injects decisions back into the coordination loop. |

All coordination — task assignment messages, status updates, conflict alerts, handoffs — flows **through Band** as structured context, making the collaboration visible, auditable, and framework-agnostic.

## Architecture

See [`ARCHITECTURE.md`](./ARCHITECTURE.md) for the full system diagram and component breakdown.

## Requirements & source of truth

Full compiled brief — tracks, Band/Codeband resources, AI/ML API partner credits, submission fields, judging criteria — in [`docs/HACKATHON_REQUIREMENTS.md`](./docs/HACKATHON_REQUIREMENTS.md).

## Submission checklist

- [ ] **≥3 agents collaborating through Band** as the core workflow (meaningful, not a wrapper)
- [ ] Basic info: title · short + long description · technology & category tags
- [ ] Cover image · video presentation · slide presentation
- [ ] **Public GitHub repository** (MIT) · demo platform · application URL
- [ ] _(Partner prize)_ meaningful **AI/ML API** usage + promo code from kickoff
- [ ] Submitted before **Jun 19, 2026, 6:00 PM TRT**

## Status

Enrolled, pre-kickoff. Band access codes + AI/ML API promo shared at the Jun 12 kickoff. See [`docs/HACKATHON_REQUIREMENTS.md`](./docs/HACKATHON_REQUIREMENTS.md).

— *Forenly · part of the [Cadence](https://github.com/Forenly) multi-hackathon initiative.*
