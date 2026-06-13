# .agentbase — DriveEasy Agentbases

This folder holds the **agentbases** for the DriveEasy Car Rental example.

An *agentbase* is a deployable home for AI agents that coordinates one slice of
the company. It binds a part of the org hierarchy (under `company/`) to the
Agentbase platform's runtime components — wikidocs, repos, harness, environments,
and deployed workforces — and exposes a **frontdesk** so other agentbases can
hand it work.

## Bases in this example

- **`base_metro_airport/`** — coordinates the **Metro Airport Branch's** rental
  operations (the Rental Counter subteam). This is the hello-world base for
  DriveEasy; only this one is fleshed out.

## What lives in a base folder

- `agentbase.md` — purpose, boundaries, and the platform slice the base uses.
- `company_self.md` — exactly where the base sits in the company hierarchy.
- `frontdesk.md` — how other agentbases reach this one and hand off work.
- `workforces/` — the workforces deployed from this base (e.g. `rental-turnaround.md`).

> Illustrative hello-world. The branch's sibling bases (Harbor Airport Branch,
> North County Airport Branch) would each get their own `base_*` folder following
> the same shape.
