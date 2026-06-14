# Frontdesk: base_bug_solving

The **frontdesk** is the single entry point other agentbases use to hand a bug to
`base_bug_solving`. Inbound reports land here, get validated and compressed (via
**headroom** — stack traces and logs get noisy fast), then route to the right
squad.

## How to reach this base
- **Address:** `base_bug_solving`
- **Serves:** Technology — Platform Engineering (the platform repos).
- **Owner of record:** Tech Lead **Omar Haddad** (escalates to CTO **Nadia Brandt**).

## Inbound handovers we accept
- **From `base_metro_airport` — a branch-surfaced bug.** e.g. the counter sees a
  wrong rate on a luxury weekly booking. The branch can't fix software; it hands
  the bug here with the rental/VIN, what was expected, and what happened.
- **From the Customer Experience base — an app/website defect.** A booking-flow or
  account bug reported by customers, with repro steps and affected accounts.
- **From the Finance & Administration base — a pricing/billing defect.** An invoice
  or pricing-engine miscalculation, with the rule and the discrepancy.
- **From monitoring — an automated alert.** A production error or regression signal.

## Outbound handovers we send
- **Back to the reporter:** the fix shipped, with the failing-then-passing test and
  the release note — so the branch / CX / Finance can confirm the symptom is gone.
- **To the Customer Experience base:** if a "bug" is actually intended behavior, we
  route it back as a product/feature question, not a code fix.

## Contract
- Every handover names the symptom, a repro (or enough to build one), the affected
  repo/area, and the desired outcome.
- The frontdesk acknowledges, the Tech Lead casts a squad, and we return status:
  triaged → reproduced (failing test) → fixed → shipped.
- Cross-base shared memory keeps prior incidents deduped, so a recurring bug is
  recognized instead of re-investigated from scratch.
