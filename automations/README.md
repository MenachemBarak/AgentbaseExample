# Automations

The **automations** folder holds the recurring, low-judgment operations DriveEasy runs
without a human kicking them off. Each automation is a **trigger -> act** pair: a
condition (schedule, event, or threshold) that fires, and the action an agent takes.
High-stakes steps hand off to `conductor` workflows or escalate per `principales/`.

## Automations (DriveEasy)
- **Pre-rental vehicle check** — *trigger:* a reservation reaches pickup-ready; *act:*
  verify telematics (fuel, mileage, clean diagnostics), confirm cleaning, then release
  the car to the Rental Counter or hold it for Vehicle Prep.
- **Daily fleet-availability sync** — *trigger:* every morning at 05:00; *act:*
  reconcile each branch's on-lot vehicles against the booking system; Sofia Marin's
  agent rebalances cars across the airport branches.
- **Overdue-return reminder** — *trigger:* a rental passes its scheduled return time;
  *act:* notify the customer, then alert the Returns & Inspection subteam.
- **Invoice-on-return** — *trigger:* vehicle returned and inspection cleared; *act:*
  finalize charges through the pricing engine and send the invoice.

Bulky telematics consumed by these automations is `headroom`-compressed first, so the
triage model stays cheap.
