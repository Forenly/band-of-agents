# Architecture — Band of Agents Hackathon (Forenly)

> Required at submission: show **Band as the coordination layer** between ≥3 specialized agents — task handoffs, shared structured context, role specialization, task state. Skeleton below; refined to the locked concept after kickoff.

## High-level flow

```
        Enterprise workflow trigger
                  │
                  ▼
        ┌───────────────────────────────────────┐
        │            BAND                        │
        │   shared interaction / coordination    │
        │   layer (agent rooms, structured        │
        │   context, recruit/discover, state)     │
        └───┬───────────┬───────────┬────────────┘
            │           │           │        cross-framework
            ▼           ▼           ▼        agent-to-agent
   ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐
   │ Agent A  │  │ Agent B  │  │ Agent C  │  │  Human   │
   │ (planner)│→ │(executor)│→ │(reviewer)│→ │ in loop  │
   └──────────┘  └──────────┘  └──────────┘  └──────────┘
        ▲  handoff   ▲  handoff   ▲  escalate
        └────────────┴────────────┘
        all coordination flows THROUGH Band
                  │
                  ▼
        Decision / output + hosted demo
```

## Components

| Component | Role |
|---|---|
| **Band** | The collaboration layer. Agents join shared rooms, exchange **structured context**, hand off tasks, coordinate **task state**, and discover/recruit peers — across frameworks. This is the judged core, not a wrapper. |
| **Specialized agents (≥3)** | Distinct roles (e.g. planner / engineer / reviewer / tester, or policy / risk / approval). Each owns a stage and passes work to the next **through Band**. |
| **Human-in-the-loop** | For escalation / decision points in regulated or high-stakes steps (Track 3) or merge approval (Track 2). |
| **Model layer (AI/ML API)** | Powers agent reasoning/extraction/summarization — meaningful use targets the **Best Use of AI/ML API** partner prize. |
| **Codeband** _(Track 2)_ | Reference implementation for multi-agent coding workflows, if building a software-delivery system. |
| **Hosted demo** | Public deployment + URL, public MIT-licensed GitHub repo, video making the multi-agent flow easy to follow. |

## Design principle (maps to judging)
Collaboration must be **visible, useful, and central** — Band carries the handoffs *during* the workflow, agents specialize by role, context flows as structured state, and the system goes beyond linear automation (discover, divide, review, escalate, collaborate across frameworks).

_(Diagram and detail to be completed after the kickoff and concept lock.)_
