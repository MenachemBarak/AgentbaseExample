# Frontdesk: base_metro_airport

The **frontdesk** is the single entry point other agentbases use to hand work to
`base_metro_airport`. Inbound requests land here, get validated and compressed
(via **headroom**), then route to the right workforce or branch role.

## How to reach this base
- **Address:** `base_metro_airport`
- **Serves:** Metro Airport Branch — Rental Counter (+ Vehicle Prep, Returns & Inspection).
- **Hours:** branch operating hours; after-hours requests queue to mission control.
- **Owner of record:** Branch Manager **Aisha Khan**.

## Inbound handovers we accept
- **From the Fleet Management base — vehicle availability.** Which VINs are inbound,
  due back, or pulled for service. Our Regional Fleet Coordinator **Sofia Marin**
  reconciles this across West branches so the counter never promises a car we don't
  have. Telematics payloads (location, mileage, fuel, diagnostics) are compressed on arrival.
- **From the Customer Experience base — support escalation.** A brand-level support
  case that needs branch action (a stranded customer, a vehicle swap, a counter
  exception). Long chat transcripts are deduped and compressed before they reach a
  counter agent.
- **From the Finance & Administration base — billing & pricing notes.** Invoice
  holds, pricing-engine overrides, or damage-charge approvals tied to a rental.

## Outbound handovers we send
- **To Fleet Management:** a car is back-to-available, or a car needs maintenance
  (failed inspection / diagnostic flag).
- **To Customer Experience:** the counter couldn't resolve an issue locally — escalate.
- **To Finance & Administration:** a finalized return with damage findings, ready to bill.

## Contract
- Every handover names a rental/VIN, a reason, and a desired outcome.
- The frontdesk acknowledges, assigns to a workforce or role, and returns a status.
- Cross-base shared memory keeps customer rental history deduped, so a handover
  never re-sends what another base already knows.
