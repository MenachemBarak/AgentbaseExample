# Team — Platform Engineering

## Overview
**Platform Engineering** is the team inside the **Technology** division that owns
DriveEasy's platform code end to end. It builds features and **fixes the bugs** that
reach customers and branch staff, working against the four platform repos:
`booking-system`, `pricing-engine`, `counter-terminal`, and `fleet-telematics`. The
team is led by Tech Lead **Omar Haddad** under CTO **Nadia Brandt**.

## How it works
Every change runs through the same path: a bug or feature lands, an engineer picks
it up against the relevant repo, validates it in `environments/`, and ships it once
it is proven. The team's day-to-day agentic work is declared as **bridges** under
[`agentic_bridge/driveeasy_bridge/`](../../../../../agentic_bridge/driveeasy_bridge/):
the **bug-solving squad** (`bridge/bug-solving/`) mirrors this team's roles onto
[bradygaster/squad](https://github.com/bradygaster/squad) so a single human can run
a coordinated set of specialist agents to triage and fix a bug.

## Purpose & goals
- Keep the platform repos green and production healthy.
- Turn reported bugs into verified fixes quickly, with a clear owner per bug.
- Ship features for the other divisions without regressions.
- Run the bug-solving squad as the team's standard way of resolving incidents.

## Roles
Five roles make up the team — see [roles.md](roles.md). These are exactly the roles
the bug-solving squad's members bind to:

- **role_tech-lead** — Omar Haddad (leads the team and the squad)
- **role_frontend-engineer** — front-end of booking-system / counter-terminal
- **role_backend-engineer** — back-end of booking-system / pricing-engine
- **role_qa-engineer** — reproduction, tests, and verification
