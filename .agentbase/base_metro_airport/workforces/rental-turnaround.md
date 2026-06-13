# Workforce: rental-turnaround

A deployed workforce in `base_metro_airport` that turns a just-returned vehicle
back into a rentable one: **return → inspect → clean → refuel → back-to-available**.

## Mission
Every car dropped at the Metro Airport return lot becomes a safe, clean, fueled,
bookable vehicle in the shortest time quality allows — so the Rental Counter always
has cars to rent and customers get on the road quickly.

## Definition of Done (DoD)
A vehicle is "back-to-available" only when ALL hold:
- Return logged against the rental; telematics captured (mileage, fuel, diagnostics).
- Inspection complete; damage is either **none** or **approved through the human gate**.
- Cleaned to branch standard and refueled/charged to ready level.
- No open diagnostic flags; otherwise the car is routed to Fleet Management for maintenance.
- Status flipped to **available** in the booking system; the counter is notified.

## Orchestration (conductor)
The turnaround runs as a **deterministic DAG** defined in the **conductor**
framework: `return → inspect → clean → refuel → back-to-available` (conductor may
run clean and refuel in parallel once inspection clears). Routing is fixed,
version-controlled Jinja2 — not an LLM guessing the next step — so every car
follows the same repeatable path.
- **Human-in-the-loop gate (damage approval):** at **inspect**, if damage is found
  the flow pauses. **Returns & Inspection** raises the finding; Branch Manager
  **Aisha Khan** (or Counter Lead **Grace Liu** on shift) approves before any
  customer is charged. Only then does the Finance & Administration billing handover fire.

## Components it builds on
- **company roles:** Returns & Inspection and Vehicle Prep subteams; counter kept
  in the loop by **Ben Foster**; damage gate owned by **Grace Liu** / **Aisha Khan**.
- **wikidocs:** return-lot checklist, inspection rubric, clean/refuel standards.
- **repos:** automation that reads telematics, updates the booking system, and opens maintenance tickets.
- **environments:** dry-runs in sandbox, then the live branch return lot.
- **harness:** replays real past returns (including damage cases) to validate the DAG and the gate before deployment.
- **agentic_bridge:** **headroom** compresses telematics and maintenance logs; **conductor** runs the workflow.

## Mission control
Mission control shows the live DAG for every vehicle in turnaround — current step,
cars waiting on the damage gate, and time-to-available — so **Tom Becker** (Group
Ops Supervisor) and **Aisha Khan** can spot bottlenecks and keep the counter stocked.
