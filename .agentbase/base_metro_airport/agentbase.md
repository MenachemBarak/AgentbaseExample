# Agentbase: base_metro_airport

## Overview
`base_metro_airport` is the agentbase that coordinates day-to-day **rental
operations for the Metro Airport Branch** of DriveEasy Car Rental. It gives the
branch's AI agents one home: shared knowledge, the systems they act on, the
workforces they run, and a frontdesk other bases talk to.

## Purpose
- Drive the branch rental lifecycle on the ground: reserve → pickup → in-use → return → invoice.
- Keep the Rental Counter staffed by agents that mirror real branch roles.
- Turn returned vehicles back into available, rentable cars quickly and safely.

## Boundaries — what this base owns / does not own
- **Owns:** counter check-in/check-out, branch-local booking actions, the vehicle
  return-to-ready turnaround, and branch shift logs.
- **Does NOT own:** fleet sizing and cross-branch car balancing (Fleet Management),
  brand-wide customer support and loyalty (Customer Experience), or pricing-engine
  rules and billing (Finance & Administration). Those arrive through the frontdesk.
- **Scope is one branch.** Siblings (Harbor Airport, North County Airport) run
  their own bases.

## Platform slice this base uses
- **company roles** — agents are bound to Metro Airport Branch + Rental Counter roles.
- **wikidocs** — branch SOPs, counter scripts, the return-lot checklist.
- **repos** — branch automation that calls the booking system, counter terminals, and telematics.
- **environments** — a sandbox for training/QA and the live branch environment.
- **harness** — replays past rentals and returns to test agents before they go live.
- **workforces** — deployed agent teams (see `workforces/`), watched from **mission control**.
- **agentic_bridge** — headroom (compress telematics & chat), squad (role-mirrored teams), conductor (lifecycle DAGs).

## Children
See `workforces/` for deployed workforces — starting with `rental-turnaround.md`.
