# Setup — the bug-solving squad

This bridge declares a **squad** ([bradygaster/squad](https://github.com/bradygaster/squad))
for DriveEasy: a human-led team of specialist AI agents that **triage and fix a
production bug** on the platform repos. The machine-readable declaration is in
[`frameworks.yaml`](frameworks.yaml); this file explains it.

## The idea

squad gives one person a coordinated set of specialist agents (lead, frontend,
backend, tester, scribe) that live as files in the repo, each in its own context,
tracked in git. The key DriveEasy move: **the specialists are not generic — they
are bound to the company's own roles**. The squad mirrors the **Technology →
Platform Engineering** team exactly, so the agentic setup and the org chart never
drift apart.

## Member → company role binding

| squad agent | Company role | Holder | Role file |
|---|---|---|---|
| **lead** | `role_tech-lead` | Omar Haddad | […/role_tech-lead.md](../../../../company/divisions/technology/teams/platform-engineering/roles/role_tech-lead.md) |
| **frontend** | `role_frontend-engineer` | Lena Fischer | […/role_frontend-engineer.md](../../../../company/divisions/technology/teams/platform-engineering/roles/role_frontend-engineer.md) |
| **backend** | `role_backend-engineer` | Raj Mehta | […/role_backend-engineer.md](../../../../company/divisions/technology/teams/platform-engineering/roles/role_backend-engineer.md) |
| **tester** | `role_qa-engineer` | Yuki Tanaka | […/role_qa-engineer.md](../../../../company/divisions/technology/teams/platform-engineering/roles/role_qa-engineer.md) |
| **scribe** | `role_tech-lead` | Omar Haddad | (the lead keeps the decision log in git) |

The squad is **led by** the Tech Lead (`role_tech-lead`, Omar Haddad) — one human
leads, the agents do the specialized work.

## How to set it up

1. **Pick the runtime.** Run the squad under one of the harnesses the company
   supports (e.g. Copilot CLI / Claude Code). squad works with GitHub Copilot.
2. **Materialize the repos.** `agentbase sync-all` clones the platform repos from
   [`repos/repos.yaml`](../../../../repos/repos.yaml) into `repos/internal/`
   (`booking-system`, `pricing-engine`, `counter-terminal`, `fleet-telematics`).
3. **Seed each squad agent from its role file.** For every row above, give the
   agent the responsibilities/purpose from its `company/` role file as its brief —
   so the `frontend` agent behaves like DriveEasy's actual front-end engineer.
4. **Add context compression.** Wire `headroom` (from
   `agentic_bridge/frameworks/context_compression/headroom/`) so the agents'
   logs, stack traces, and telematics dumps are compressed before they hit the
   model — bug tickets get noisy fast.
5. **Run it human-led.** Omar (lead) sets the goal and approves the fix; the
   engineers work their layer; Yuki (tester) gates on a failing-then-passing test.

## The rule this demonstrates

A squad is **declared**, not improvised: a `frameworks.yaml` that names the
framework(s) and **binds each agent to a real `company/` role**, plus a `setup.md`
that says how to wire it to the company's repos and harness. That is how, per
`HOW_TO_USE_AGENTBASE.md`, an agentic transformation is expressed — Layer-1
(`bridge` + `company` + `repos`) composed into a concrete, repeatable team.
