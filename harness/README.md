# Harness

The **harness** folder declares the agent *runtimes* DriveEasy's agents run under —
the CLIs and SDKs that actually execute a role's reasoning loop — and pins **which
model handles which task**. AgentBase keeps this separate from the org hierarchy so
the same role (e.g. `role_rental-agent`) can switch harness or model without
rewriting its responsibilities.

## Supported harnesses
- **Claude Code** — frontier reasoning for the heavy work: damage adjudication,
  rental-contract interpretation, dispute handling.
- **Copilot CLI** — repo-bound automation and code changes across the booking
  system and pricing engine (pairs with the `squad` and `conductor` bridges).

## Model-per-task policy (DriveEasy)
- **Cheap / fast model** — high-volume, low-stakes: GPS telematics triage, fuel &
  mileage parsing, overdue-return reminders, fleet-availability sync.
- **Frontier model** — low-volume, high-stakes: damage/contract reasoning at the
  return lot, fraud review, customer-escalation responses.

Cheap passes feed on `headroom`-compressed telematics so even frontier reasoning
stays affordable. See `principales/` for the escalation rules that decide when to
upgrade the model.
