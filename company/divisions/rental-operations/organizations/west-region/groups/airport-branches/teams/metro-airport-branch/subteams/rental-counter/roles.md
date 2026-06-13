# Rental Counter — Roles

The Rental Counter runs as a small shift crew: one lead directing a line of
associates who do the hands-on customer check-in and check-out.

## Role hierarchy
- **role_counter-lead** — *Grace Liu*, Counter Team Lead. Runs the front counter
  shift; owns queue flow, escalations, and the till.
  - **role_rental-associate** — *Ben Foster*, Rental Counter Associate. Checks
    customers in and out at the desk.

The Counter Team Lead reports up to Branch Manager **Aisha Khan** of the Metro
Airport Branch.

## Collaboration & communication
- **Within the subteam:** the Lead assigns positions and break rotations at shift
  start, then works the floor — clearing escalations (declined cards, license
  problems, upgrade disputes) that associates raise. Quick verbal handoffs plus a
  shared shift log keep everyone aligned.
- **With sibling subteams:** the counter signals **Vehicle Prep** when a class is
  running low or a staged car is needed, and passes returning customers to
  **Returns & Inspection** at drop-off.
- **Up the hierarchy:** the Lead reports counter status, staffing gaps, and
  customer issues to Branch Manager Aisha Khan, and works alongside the branch's
  Rental Sales Agents (exemplar **Diego Alvarez**).
- **Tooling:** counter terminals share one deduped customer history via
  **headroom**; the desk's check-in/out steps are the customer-facing nodes of
  the branch's **conductor** rental-lifecycle workflow, which holds a
  human-in-the-loop gate for damage review before any final charge.

See `roles/role_counter-lead.md` and `roles/role_rental-associate.md` for full
definitions.
