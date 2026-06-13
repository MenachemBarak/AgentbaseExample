# Repos

The **repos** folder lists the code repositories DriveEasy's agents read, modify, and
ship against. Each repo is a workspace a `harness/` can be pointed at; agents from the
matching role operate inside it. Repos are split into `internal/` (proprietary,
private) and `opensource/` (public or vendored upstreams).

## internal/
- **booking-system** — reservations, customer accounts, and the reserve -> pickup ->
  in-use -> return -> invoice lifecycle.
- **fleet-telematics** — ingests GPS location, mileage, fuel, and diagnostics from
  every vehicle; the bulkiest data source (compressed via `headroom`).
- **pricing-engine** — dynamic rates by vehicle class (economy, compact, SUV,
  luxury, van), branch demand, and season.
- **counter-terminal** — the branch counter check-in/out app used at Metro Airport.

## opensource/
- Vendored SDKs and the three agentic_bridge frameworks (`headroom`, `squad`,
  `conductor`) the bases build on.

Branch teams own their slice: the Rental Counter subteam touches `counter-terminal`,
while Sofia Marin's fleet coordination work lives in `fleet-telematics`.
