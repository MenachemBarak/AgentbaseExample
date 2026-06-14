# driveeasy_bridge — DriveEasy's company bridge

This is **DriveEasy's own bridge** — the company-specific layer that adapts the
built-in agentic frameworks (under `agentic_bridge/frameworks/`) to *DriveEasy's*
roles, repos, and workflows. The frameworks alone are generic; a framework only
becomes useful here once it is built around the company hierarchy in `company/`.
That adaptation lives here.

## Structure

```
driveeasy_bridge/
    README.md            - this file
    bridge/              - one folder per purpose-built combination of frameworks
        bug-solving/     - the bug-solving squad (declared below)
            frameworks.yaml   - which frameworks this bridge is built on
            setup.md          - how it maps onto company/ roles and repos
            use_cases/        - how specific jobs are handled
                solve-bug.md
```

## Bridges

| Bridge | Built on | What it does |
|---|---|---|
| **bug-solving** | `squad` (+ `headroom`) | A human-led squad that triages and fixes a production bug on the platform repos. Its members are the **Platform Engineering** team's roles. See [`bridge/bug-solving/`](bridge/bug-solving/). |

## How a bridge here relates to the company

A bridge under `driveeasy_bridge/` never invents people. Each agent in a bridge is
**bound to a real role** defined in `company/` — so the org chart and the agentic
setup stay in lock-step. The bug-solving squad, for example, binds its lead to
`role_tech-lead`, its engineers to `role_frontend-engineer` / `role_backend-engineer`,
and its tester to `role_qa-engineer`, all in the **Technology → Platform
Engineering** team. Change the role, and the squad changes with it.
