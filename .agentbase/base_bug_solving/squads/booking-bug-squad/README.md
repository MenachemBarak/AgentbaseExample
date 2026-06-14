# Squad: booking-bug-squad

A **deployed squad** in `base_bug_solving`. It triages and fixes production bugs
on DriveEasy's platform repos, human-led, with a failing-test gate before
anything ships.

This folder uses **[squad](https://github.com/bradygaster/squad)'s native format**
— a `.squad/team.md` roster plus one `.squad/agents/<name>/charter.md` per member —
exactly what `squad init` would scaffold in a working repo. The difference from a
vanilla squad: **each member's charter is derived from a real DriveEasy company
role**, so the squad mirrors the Technology → Platform Engineering team.

## How this squad references the rest of the Agentbase

| Squad member | Company role it mirrors | Holder |
|---|---|---|
| Lead | [`role_tech-lead`](../../../../company/divisions/technology/teams/platform-engineering/roles/role_tech-lead.md) | Omar Haddad |
| Frontend | [`role_frontend-engineer`](../../../../company/divisions/technology/teams/platform-engineering/roles/role_frontend-engineer.md) | Lena Fischer |
| Backend | [`role_backend-engineer`](../../../../company/divisions/technology/teams/platform-engineering/roles/role_backend-engineer.md) | Raj Mehta |
| Tester | [`role_qa-engineer`](../../../../company/divisions/technology/teams/platform-engineering/roles/role_qa-engineer.md) | Yuki Tanaka |
| Scribe | (Lead, keeping the decision log) | Omar Haddad |

- **Framework:** [`squad`](../../../../agentic_bridge/frameworks/agentic_teams/squad/),
  adapted for DriveEasy in [`driveeasy_bridge`](../../../../agentic_bridge/driveeasy_bridge/).
- **Repos it operates on:** `booking-system`, `pricing-engine`, `counter-terminal`,
  `fleet-telematics` (from [`repos/repos.yaml`](../../../../repos/repos.yaml)).
- **Context compression:** `headroom`, so long traces and logs stay in budget.

## How it runs (squad's real flow)
1. `squad init` scaffolds `.squad/` in the target repo (here it is committed as the
   base's declared roster).
2. The **Lead** (`role_tech-lead`) casts members per the roster and sets the goal.
3. Members work their layer; the **Tester** holds the failing-then-passing gate.
4. The **Scribe** records decisions in `.squad/decisions.md`; the Lead ships.

See [`.squad/team.md`](.squad/team.md) for the roster and the per-member charters
under [`.squad/agents/`](.squad/agents/).
