# conductor

**conductor** is "a CLI tool for defining and running multi-agent workflows with
the GitHub Copilot SDK and Anthropic Claude." You define your agents, their
prompts, and the routing between them in a single YAML file. Routing is driven
by Jinja2 templates and expressions — *not* by an LLM deciding the next step — so
pipelines are repeatable, deterministic, and version-controlled. conductor
supports parallel and sub-workflow execution, conditional routing,
human-in-the-loop gates, and a real-time web dashboard that renders the workflow
as a DAG graph.

**Category:** `workflow_managment`

https://github.com/microsoft/conductor

## How DriveEasy uses it
DriveEasy models the entire **rental lifecycle** as one deterministic conductor
DAG. Each stage is an agent step and the routing between stages is fixed in YAML,
so every rental follows the same auditable path:

```
reserve ──> pickup ──> in-use ──> return ──> [ damage review ] ──> invoice
                                                  ⛔ human-in-the-loop gate
```

- **reserve** — the booking system holds a vehicle of the requested class.
- **pickup** — the counter terminal checks the customer out and assigns the car.
- **in-use** — GPS telematics track location, mileage, and fuel during the rental.
- **return** — the return lot logs the car back in and Returns & Inspection checks it.
- **damage review (human gate)** — before any charge, a branch staffer must
  approve or reject reported damage. conductor pauses the DAG here until a person
  decides; nothing proceeds automatically.
- **invoice** — only after approval does the pricing engine generate the final charge.

The gate is expressed in the same YAML that defines the pipeline:

```yaml
# rental_lifecycle.yaml (excerpt) — routing is Jinja2, not an LLM
routing:
  return:
    - when: "{{ damage_reported }}"
      gate: human          # pause for damage review/approval
      then: invoice
    - else: invoice
```

Because routing is deterministic, the same lifecycle runs identically for an
economy compact or a luxury SUV and every run is reproducible — while the one
step that genuinely needs judgment, the damage decision, is explicitly handed to
a human before the customer is charged.
