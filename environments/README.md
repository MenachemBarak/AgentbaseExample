# Environments

The **environments** folder defines *where* DriveEasy's agents are allowed to run and
how risky each target is. Agents do work in the lowest-risk environment that can
prove the result, then promote upward. Each environment lists setup steps, the
permissions it grants, and how to capture **proof** that the work succeeded.

## Environments (DriveEasy)
- **booking-system sandbox** — disposable, seeded with fake reservations. Anyone may
  write. *Proof:* test-run logs, sandbox reservation IDs.
- **booking-system staging** — production-like with anonymized data. Writing requires
  a passing sandbox run. *Proof:* staging screenshots + green CI from `repos/`.
- **branch-terminal staging** — a mirrored Metro Airport counter terminal for
  check-in/out flows. *Proof:* a recorded terminal session.
- **live production booking** — real customers, real money. **Read-mostly;** writes
  require a human-in-the-loop gate (see `conductor`) and an approved staging proof.

## Permissions & proof
Promotion is one step at a time: sandbox -> staging -> production. Each step attaches
its proof artifact; production changes also record the approver (e.g. Aisha Khan for
the Metro Airport branch). See `security/` for credential handling.
