# Technology Division

## Overview
The **Technology** division builds and maintains the software DriveEasy runs on —
the **booking-system**, the **pricing-engine**, the **counter-terminal** app, and
the **fleet-telematics** pipeline. Where the other four divisions *use* these
platforms to rent cars, Technology *owns the code*: it ships features, keeps
production healthy, and fixes the bugs that reach customers and branch staff. It is
led by **CTO Nadia Brandt**, who is also an active code contributor.

## How it works
Technology is organized as a single delivery unit — the **Platform Engineering**
team — that owns the platform repos end to end. The team works against the
repositories declared in [`repos/repos.yaml`](../../../repos/repos.yaml)
(`booking-system`, `pricing-engine`, `counter-terminal`, `fleet-telematics`),
runs on the harnesses declared under `agentic_bridge/.../harness/`, and validates
changes in `environments/` before they reach production. Most of its agentic
transformation is declared as **bridges** under
[`agentic_bridge/driveeasy_bridge/`](../../../agentic_bridge/driveeasy_bridge/) —
for example the **bug-solving squad**.

## Purpose & goals
- Keep the rental platform reliable: triage and fix production bugs fast, before
  they cost bookings.
- Ship the features the other divisions need (new pricing rules, kiosk flows,
  telematics signals) without regressions.
- Make the platform observable and safe to change — tests, environments, and
  guardrails over heroics.
- Lead DriveEasy's agentic transformation of platform maintenance and development.

## Vision
A rental platform that fixes and improves itself at the speed of the business —
where every bug has an owner and every change is proven before it ships.

## Mission
Build, run, and continuously repair the software DriveEasy rents cars on, turning
incidents and feature requests into shipped, verified changes.

## Teams
Technology delivers through one team today:

- **Platform Engineering** — owns the platform repos, ships features, and runs the
  bug-solving squad. See [teams/platform-engineering/team.md](teams/platform-engineering/team.md).
