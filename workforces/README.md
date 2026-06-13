# Workforces

The **workforces** folder defines reusable *subsets* of agents that can be dropped into
any DriveEasy base or branch, instead of rebuilding the same team each time. A
workforce bundles roles, their plugins, and their playbooks into a portable unit — the
company org hierarchy says *who reports to whom*, while a workforce says *here is a
ready-made crew for a recurring job*.

## Reusable workforces (DriveEasy)
- **customer-support** — handles bookings, changes, and complaints across phone, chat,
  and counter; reused by every branch and by corporate-account clients. Pairs with
  `wikidocs/public` and `headroom`-compressed chat transcripts.
- **vehicle-inspection** — runs pre-rental checks and return-lot damage review using
  the photo damage-detection plugin; shared by the Returns & Inspection and Vehicle
  Prep subteams.
- **fleet-rebalancing** — a telematics-driven crew that redistributes vehicles between
  branches under Sofia Marin.

## How they're used
A branch like Metro Airport instantiates a workforce, binds it to its local
`environments/` and `repos/`, and the same definition serves the Harbor Airport and
North County Airport branches — consistency without copy-paste.
