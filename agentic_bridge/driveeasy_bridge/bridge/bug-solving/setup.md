# Setup — DriveEasy's bug-solving squad pattern

This bridge folder is the **adaptation pattern**: how DriveEasy binds the generic
[`squad`](https://github.com/bradygaster/squad) framework to its own company roles
and repos. It is **not** the deployment — the live squad is deployed in a base:

> **Deployment:** [`.agentbase/base_bug_solving/squads/booking-bug-squad/`](../../../../.agentbase/base_bug_solving/squads/booking-bug-squad/)
> contains the real squad in squad's native `.squad/` format (a `team.md` roster +
> per-member `agents/<name>/charter.md`).

The machine-readable binding is in [`frameworks.yaml`](frameworks.yaml).

## The pattern

squad gives one human a coordinated set of specialist agents (lead, frontend,
backend, tester, scribe). DriveEasy's rule: **the specialists are bound to real
`company/` roles**, so the squad mirrors the **Technology → Platform Engineering**
team and never drifts from the org chart.

| squad agent | Company role | Holder |
|---|---|---|
| lead | `role_tech-lead` | Omar Haddad |
| frontend | `role_frontend-engineer` | Lena Fischer |
| backend | `role_backend-engineer` | Raj Mehta |
| tester | `role_qa-engineer` | Yuki Tanaka |
| scribe | `role_tech-lead` (decision log) | Omar Haddad |

The role files live under
`company/divisions/technology/teams/platform-engineering/roles/`.

## How a base uses this pattern

1. A base whose purpose needs a squad (here, `base_bug_solving`) declares the squad
   under its `squads/` folder in squad's native `.squad/` format.
2. Each member's `charter.md` is **derived from the company role** named above —
   that is this pattern applied.
3. The base wires the squad to its repos (`booking-system`, `pricing-engine`,
   `counter-terminal`, `fleet-telematics`) and to `headroom` for context
   compression, then runs it human-led, with the Tester's failing-test gate.

So: **framework** (squad) → **pattern** (this bridge: bind to company roles) →
**deployment** (`base_bug_solving`'s `.squad/`). See
[`use_cases/solve-bug.md`](use_cases/solve-bug.md) for a concrete run.
