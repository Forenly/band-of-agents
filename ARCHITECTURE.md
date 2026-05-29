# Architecture — RoboFleet Coordinator (Band of Agents Hackathon)

> Required at submission: show **Band as the coordination layer** between ≥3 specialized agents — task handoffs, shared structured context, role specialization, task state. Skeleton below; refined to the locked concept after kickoff.

## High-level flow

```
        Incoming mission (inspection / delivery / patrol)
                          │
                          ▼
        ┌──────────────────────────────────────────────────┐
        │                    BAND                           │
        │   shared interaction / coordination layer         │
        │   (agent rooms · structured task state ·          │
        │    spatial context · recruit/discover · handoffs) │
        └───┬──────────────┬────────────────┬──────────────┘
            │              │                │        cross-framework
            ▼              ▼                ▼        agent-to-agent
   ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
   │ Fleet Planner│  │ Robot Agent  │  │  Conflict    │
   │              │→ │   ×N         │→ │  Resolver    │
   │  allocate /  │  │  execute /   │  │  detect /    │
   │  re-prioritize│ │  report      │  │  negotiate   │
   └──────────────┘  └──────────────┘  └──────────────┘
            │              │                │
            └──────────────┴────────────────┘
                           │  unresolvable conflict / safety flag
                           ▼
                  ┌──────────────────┐
                  │  Human Operator  │
                  │  (HITL)          │
                  │  escalation +    │
                  │  priority inject │
                  └──────────────────┘
                           │
                           ▼
                  Fleet state update + mission output
```

## Components

| Component | Role |
|---|---|
| **Band** | The coordination layer. Agents join a shared fleet room, exchange **structured task state** (mission ID, robot ID, position, payload, status), hand off tasks, detect/resolve conflicts, and escalate — across frameworks. This is the judged core, not a wrapper. |
| **Fleet Planner** | Receives incoming missions. Scores available robots on proximity, capacity, and current load. Emits allocation decisions and re-prioritizes in response to robot status changes — all through Band. |
| **Robot Agent ×N** | Each represents one physical or simulated robot. Accepts task assignments from Band, reports position/status updates back, and requests help when blocked or when a conflict is detected. Multiple robot agents run concurrently. |
| **Conflict Resolver** | Monitors shared spatial state in Band. Detects resource contention (path collision, dock conflict, competing priorities) and negotiates resolution between robot agents. Escalates to the human operator when autonomous resolution fails. |
| **Human Operator (HITL)** | Receives a structured escalation packet from Band (conflict summary, robot states, recommended options). Injects a decision back into the Band room; the Conflict Resolver propagates it to the affected robot agents. |
| **Model layer (AI/ML API)** | Powers agent reasoning — mission scoring, conflict classification, route suggestion. Meaningful AI/ML API usage targets the **Best Use of AI/ML API** partner prize. |
| **Codeband** _(Track 2 cross-leverage)_ | Reference implementation patterns for multi-agent coordination; applied to the planning and simulation tooling. |
| **Hosted demo** | Public deployment + URL, public MIT-licensed GitHub repo, video making the multi-agent coordination flow easy to follow. |

## Design principle (maps to judging)

Collaboration must be **visible, useful, and central** — Band carries every handoff during live fleet operation. Agents specialize by role (plan / execute / resolve / approve). Context flows as structured state. The system goes well beyond linear automation: agents discover peers, divide work dynamically, re-route on failure, and escalate with full context — all through Band.

_(Diagram and detail to be completed after the kickoff and concept lock.)_
