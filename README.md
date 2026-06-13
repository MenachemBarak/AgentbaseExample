# AgentbaseExample — DriveEasy Car Rental

Example of a rental company who decided to use **[AgentBase](https://github.com/MenachemBarak/agentbase)**.
The company has a **rental-car platform** + **administrative work**.

This repository is a complete, ready-to-read **AgentBase project**: it shows how a
real business — *DriveEasy Car Rental* — models its company, wires in cutting-edge
agentic frameworks, and runs an agentic workforce on top of AgentBase.

> It is consumed by the main AgentBase repo as a git submodule under
> `examples/carrental/`, but it also stands on its own here.

## The company

**DriveEasy Car Rental** rents vehicles (economy → luxury, plus vans) from
branches at airports, downtown, and the suburbs. Every rental follows the same
lifecycle: **reserve → pickup → in-use → return → invoice**. The business splits
into two halves, both represented here:

- **Rental-car platform** — the booking system, pricing engine, branch counter
  terminals, and the GPS telematics on every car. (See `company/` → *Customer
  Experience* and *Fleet Management*, and the workforce in `.agentbase/`.)
- **Administrative work** — pricing economics, invoicing, accounting, legal, and
  compliance. (See `company/` → *Finance & Administration*, plus `complience/`,
  `security/`, `stakeholders/`.)

## What's inside

| Path | What it shows |
| --- | --- |
| `company/` | The org hierarchy — Company → Division → Organization → Group → Team → Subteam — fully detailed down one vertical slice (Rental Operations → West Region → Airport Branches → Metro Airport Branch → Rental Counter), with roles at every level. |
| `.agentbase/` | The hello-world **base**: a deployed agentic workforce (`rental-turnaround`) that turns a returned car back into a rentable one. |
| `agentic_bridge/` | The three real frameworks AgentBase bridges in — **headroom** (context compression), **squad** (agent teams), **conductor** (workflow DAGs) — each re-cast for car-rental use. |
| `harness/` `repos/` `automations/` `environments/` `plugins/` `principales/` `security/` `complience/` `wikidocs/` `workforces/` `stakeholders/` | The supporting AgentBase building blocks, themed for a rental company. |

## How to read it

Start at [`company/company.md`](company/company.md) for the whole company, then
[`company/divisions/divisions.md`](company/divisions/divisions.md) for the four
divisions, and follow **Rental Operations** down the hierarchy. Then see
[`.agentbase/`](.agentbase/) for the workforce that ties it together.
