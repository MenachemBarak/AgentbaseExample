# Principales

The **principales** folder encodes the operating principles every DriveEasy agent must
obey — the guardrails that hold regardless of role, harness, or task. Each principle
is a short policy file agents load before acting.

## Principles (DriveEasy)
- **Escalation** — when stakes exceed a role's authority (damage dispute, large
  refund, fraud signal), hand up the chain: associate -> counter lead (Grace Liu) ->
  branch manager (Aisha Khan) -> regional.
- **Limitations** — agents never alter signed rental agreements or charge a card
  outside the approved invoice flow.
- **Security** — payment, PII, and driver's-license data follow `security/` rules; no
  raw card numbers in logs or context.
- **Permissions** — act in the lowest-risk `environments/` first; production writes
  need approval.
- **Solveability** — if a task can't be completed with the available tools or data,
  stop and report rather than guess a customer charge.
- **Validation** — verify vehicle, customer, and price against the booking system
  before pickup or invoice.
- **QualityGates** — every return must pass inspection and damage review before
  billing.
- **SelfEvolve** — mine failed sessions (via `headroom learn`) to improve the
  playbooks in `wikidocs/`.
