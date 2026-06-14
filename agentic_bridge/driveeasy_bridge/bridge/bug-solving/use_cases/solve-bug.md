# Use case — solve a production bug

A concrete run of the **bug-solving squad** (declared in
[`../frameworks.yaml`](../frameworks.yaml)). It shows how the bound company roles
work a real DriveEasy bug end to end.

## The bug

> **BOOK-1473** — At the Metro Airport Branch counter, applying a weekly rate to a
> luxury-class booking sometimes charges the daily rate on the final invoice.
> Reported by Counter Team Lead **Grace Liu**; it has cost three disputed invoices
> this week.

This spans the UI (`counter-terminal`), the services (`booking-system`), and the
rate math (`pricing-engine`) — exactly why a *squad* fits better than one agent.

## How the squad works it

1. **Lead (Omar Haddad, `role_tech-lead`)** takes the report, scopes it to the
   reserve→invoice path, and sets the squad's goal: *reproduce, fix, prove, ship*.
2. **Tester (Yuki Tanaka, `role_qa-engineer`)** reproduces BOOK-1473 and writes a
   **failing test**: luxury + weekly rate → invoice must equal the weekly total.
3. **Backend (Raj Mehta, `role_backend-engineer`)** traces it into `pricing-engine`:
   the weekly rate is selected but a rounding branch falls back to the daily rate
   for the luxury class. He fixes the calculation in `booking-system`/`pricing-engine`.
4. **Frontend (Lena Fischer, `role_frontend-engineer`)** confirms `counter-terminal`
   sends the rate selection correctly and shows the corrected quote at the desk.
5. **headroom** keeps the long stack traces, pricing logs, and booking dumps
   compressed so the agents stay within context budget while they dig.
6. **Tester** re-runs: the failing test now passes, no regressions in the rate
   suite. **Lead** approves and ships; **scribe** (the lead) logs the decision in git.

## Why this is the right shape

- **Human-led:** Omar leads exactly as he leads the Platform Engineering team —
  the squad *is* his team, mirrored onto agents.
- **Role-bound:** every agent's behavior comes from its `company/` role file, so
  the fix respects who owns what (Raj owns services/pricing, Lena owns the UI).
- **Proven, not hopeful:** nothing ships until the QA engineer's failing test
  passes — the same gate the real team uses.
- **Disposable:** when BOOK-1473 is closed, the squad is archived; the roles go
  back to their normal Platform Engineering work.
