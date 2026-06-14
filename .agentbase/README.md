# .agentbase — DriveEasy Agentbases

This folder holds the **agentbases** for the DriveEasy Car Rental example.

An *agentbase* is a deployable home for AI agents that coordinates one slice of
the company. It binds a part of the org hierarchy (under `company/`) to the
Agentbase platform's runtime components — wikidocs, repos, harness, environments,
and deployed workforces — and exposes a **frontdesk** so other agentbases can
hand it work.

## Bases in this example

- **`base_metro_airport/`** — coordinates the **Metro Airport Branch's** rental
  operations (the Rental Counter subteam). Its workforce turns returned cars back
  into rentable ones.
- **`base_bug_solving/`** — finds and fixes bugs in DriveEasy's **platform
  software**, run by the Technology → Platform Engineering team. It hosts a
  **squad** (in squad's native `.squad/` format) whose members mirror the
  engineering roles.

Each base has a different **purpose** and may host many agentic deployments
(squads, workflows). An agent loading this example finds the base that matches the
goal, then loads the bridges it references, then uses the right technologies.

## What lives in a base folder

- `agentbase.md` — purpose, boundaries, and the platform slice the base uses.
- `company_self.md` — exactly where the base sits in the company hierarchy.
- `frontdesk.md` — how other agentbases reach this one and hand off work.
- `workforces/` — workforces deployed from this base (e.g. `rental-turnaround.md`).
- `squads/` — squad deployments in squad's native `.squad/` format (e.g.
  `base_bug_solving/squads/booking-bug-squad/`).

A base references the wider Agentbase layer — `company/` roles, the `bridge/`
frameworks, `repos/`, `environments/`, `wikidocs/` — rather than copying it.

> Illustrative hello-world. The branch's sibling bases (Harbor Airport Branch,
> North County Airport Branch) would each get their own `base_*` folder following
> the same shape.
