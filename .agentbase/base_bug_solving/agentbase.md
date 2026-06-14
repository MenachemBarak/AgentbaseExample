# Agentbase: base_bug_solving

## Overview
`base_bug_solving` is the agentbase whose purpose is to **find and fix bugs in
DriveEasy's platform software**. Where `base_metro_airport` runs a branch on the
ground, this base runs the **Technology → Platform Engineering** team's incident
work: a reported bug enters here, and a deployed **squad** triages, fixes, proves,
and ships the resolution against the platform repos.

A base can host **many** agentic deployments. This one's home is `squads/` — it
starts with one squad (`booking-bug-squad`) and can grow more squads or workflows
as the team's bug-solving footprint expands.

## Purpose
- Turn a reported production bug into a **verified, shipped fix** — fast, with a
  clear owner per bug.
- Run a squad whose members mirror the real Platform Engineering roles, so the
  agentic team and the org chart never drift.
- Gate every fix on a failing-then-passing test before it reaches production.

## Boundaries — what this base owns / does not own
- **Owns:** triage, reproduction, fixing, and release of bugs on the platform
  repos (`booking-system`, `pricing-engine`, `counter-terminal`, `fleet-telematics`).
- **Does NOT own:** *what* a feature should do (Customer Experience), pricing
  economics (Finance & Administration), or branch operations (`base_metro_airport`).
  Those arrive as bug reports through the frontdesk and leave as shipped fixes.
- **Scope is platform code, not the business.** It changes software; it does not
  set product or pricing policy.

## Platform slice this base uses
This base **references** the wider Agentbase layer — finding the base is the first
step, then it loads the bridges, then it uses the right technologies:

- **company roles** — agents are bound to `company/divisions/technology/teams/platform-engineering`
  roles (`role_tech-lead`, `role_frontend-engineer`, `role_backend-engineer`, `role_qa-engineer`).
- **bridge** — the squad framework, adapted for DriveEasy in
  `agentic_bridge/driveeasy_bridge/`; the squad runs on
  `agentic_bridge/frameworks/agentic_teams/squad/`, with `headroom` compressing
  logs and stack traces.
- **repos** — the four platform repos from `repos/repos.yaml` (internal group).
- **environments** — sandbox/staging for reproducing and verifying fixes, then prod.
- **harness** — replays past incidents to validate a fix before release.
- **wikidocs** — runbooks, the incident rubric, and the platform's architecture notes.

## Children
See `squads/` for this base's deployed squads — starting with
[`squads/booking-bug-squad/`](squads/booking-bug-squad/), defined in squad's
native `.squad/` format.
