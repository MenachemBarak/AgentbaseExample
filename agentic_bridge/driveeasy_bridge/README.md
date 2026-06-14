# driveeasy_bridge — DriveEasy's company bridge

This is **DriveEasy's own bridge** — the company-specific layer that adapts the
built-in agentic frameworks (under `agentic_bridge/frameworks/`) to *DriveEasy's*
roles, repos, and workflows. The frameworks alone are generic; a framework only
becomes useful here once it is built around the company hierarchy in `company/`.
That adaptation lives here.

## Where the bridge sits in the layering

```
frameworks/<cat>/<name>/   - the TECHNOLOGY (generic squad/conductor/…)
driveeasy_bridge/          - the ADAPTATION (how DriveEasy binds a framework to its
                             company roles, repos, and workflows)   ← you are here
.agentbase/base_*/         - the DEPLOYMENT (a base whose purpose runs the adapted
                             framework, e.g. base_bug_solving runs a squad)
```

A bridge describes the *pattern*; a **base** is where it is actually deployed. An
agent loading this example finds the **base** for its goal, follows the base to the
**bridge** it references, and the bridge to the **framework** it is built on.

## Bridges

| Bridge | Built on | Adapts it for… | Deployed in |
|---|---|---|---|
| **bug-solving** | `squad` (+ `headroom`) | binding squad members to the **Platform Engineering** roles to fix platform bugs | [`.agentbase/base_bug_solving/`](../../.agentbase/base_bug_solving/) — see its `squads/booking-bug-squad/` (squad's native `.squad/` format) |

## How a bridge here relates to the company

A bridge under `driveeasy_bridge/` never invents people. Each agent is **bound to a
real role** in `company/` — so the org chart and the agentic setup stay in
lock-step. The bug-solving pattern binds lead → `role_tech-lead`, engineers →
`role_frontend-engineer` / `role_backend-engineer`, tester → `role_qa-engineer`,
all in **Technology → Platform Engineering**. Change the role, and the deployed
squad changes with it.
