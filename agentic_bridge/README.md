# Agentic Bridge

The **Agentic Bridge** is how DriveEasy Car Rental brings cutting-edge agentic
technology into the company without rebuilding the company around it. It is the
integration layer between the DriveEasy org hierarchy (`company/` … `subteam/`)
and best-in-class open-source agent frameworks: the org defines *who does the
work and why*, while the bridge defines *what agentic tooling powers it*.

Each supported framework is vendored as documentation under:

```
frameworks/<category>/<name>/
```

so that an agent — or a person — can discover, by category, exactly which tool
to reach for and how DriveEasy already applies it to running rentals.

## Supported frameworks

| Framework | Category | What it gives DriveEasy | Repository |
|---|---|---|---|
| **headroom** | `context_compression` | Compresses telematics streams, chat transcripts & logs before they reach branch agents | https://github.com/chopratejas/headroom |
| **squad** | `agentic_teams` | A human-led agent team mirroring the Metro Airport Branch roles | https://github.com/bradygaster/squad |
| **conductor** | `workflow_managment` | A deterministic rental-lifecycle DAG with a human damage-approval gate | https://github.com/microsoft/conductor |

## How the bridge is organized
- `frameworks/context_compression/headroom/` — keep token budgets sane.
- `frameworks/agentic_teams/squad/` — coordinate specialist agents on a project.
- `frameworks/workflow_managment/conductor/` — run repeatable multi-agent pipelines.

Every branch and regional agent in DriveEasy is expected to read this bridge
first, then pull in the framework that fits the job at hand.
