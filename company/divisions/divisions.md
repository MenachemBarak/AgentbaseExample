# DriveEasy Car Rental — Divisions

DriveEasy Car Rental is structured into **five divisions** that split the work of
renting vehicles end to end. Together they cover the full rental lifecycle —
**reserve → pickup → in-use → return → invoice** — plus the software it all runs
on, with each division owning a clear slice and handing off cleanly to the others.
All five report up to CEO **Elena Reyes**.

## Rental Operations
The customer-facing engine of the company: it runs the **regions, groups of
branches, and counters** that actually hand keys to customers. Rental Operations
owns everything that happens at a branch — staffing the counter, pickups, returns,
and local service quality. It is led by VP **Marcus Hale**, with Director of
Regional Operations **Dana Okonkwo** overseeing the regions (West, East, and
Central). *This is the fully detailed division in this example* — follow it down
through its organizations, groups, teams, and subteams for the full hierarchy.

## Fleet Management
Owns the **vehicles themselves** — procurement, registration, maintenance,
cleaning, and resale at end of life — plus the telematics that track each car's
location, mileage, fuel, and diagnostics. Fleet Management decides *what cars
exist and whether they are roadworthy*; Rental Operations decides *who gets them
and when*. The boundary: Fleet hands a ready, healthy vehicle to a branch lot, and
the branch takes over from there.

## Customer Experience
Owns the **customer journey across channels** — the booking system's front end,
the website and app, the loyalty program, and post-rental support. Customer
Experience shapes *how customers find, book, and feel about DriveEasy*; Rental
Operations delivers the in-person moment at the counter. The boundary: CX owns the
digital and support experience around a rental, Operations owns the physical
handoff of the car.

## Finance & Administration
Owns the **money and the rules** — the economics behind the pricing engine,
invoicing and payments, accounting, legal, and compliance. Finance &
Administration sets *the pricing models and financial guardrails*; Operations and
Customer Experience apply them at the point of sale. The boundary: Finance defines
fair, profitable pricing and closes the books, while the other divisions execute
within those limits.

## Technology
Owns the **software DriveEasy runs on** — the `booking-system`, `pricing-engine`,
`counter-terminal`, and `fleet-telematics` repos. Where the other four divisions
*use* these platforms, Technology *owns the code*: shipping features, keeping
production healthy, and fixing the bugs that reach customers and branch staff. It
is led by **CTO Nadia Brandt** (an active code contributor) through the **Platform
Engineering** team. The boundary: the business divisions decide *what* the software
must do; Technology owns *how* it is built and repaired. This is where DriveEasy's
agentic transformation of platform maintenance lives — see the **bug-solving
squad** under `agentic_bridge/driveeasy_bridge/`.

## How the boundaries fit together
A typical rental crosses all four operational divisions: **Customer Experience**
captures the booking, **Fleet Management** supplies a ready vehicle, **Rental
Operations** checks the customer in and out at the branch, and **Finance &
Administration** prices the deal and issues the invoice — all running on platforms
that **Technology** builds and keeps healthy. Clean handoffs between these divisions
are what make a DriveEasy rental feel effortless.
