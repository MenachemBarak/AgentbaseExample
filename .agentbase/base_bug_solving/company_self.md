# Company Self: base_bug_solving

This file pins `base_bug_solving` to its exact place in the DriveEasy Car Rental
org hierarchy. The base serves the **Platform Engineering** team of the
**Technology** division — the people (and now agents) who own and repair the
software the whole company rents cars on.

**Slice served:** Technology › Platform Engineering

## Position in the hierarchy

```
DriveEasy Car Rental — CEO: Elena Reyes
└─ Division: Technology — Nadia Brandt (CTO)
   └─ Team: Platform Engineering — Omar Haddad (Tech Lead)
      ├─ role_frontend-engineer — Lena Fischer
      ├─ role_backend-engineer  — Raj Mehta
      └─ role_qa-engineer       — Yuki Tanaka
```

## What part this base serves
- **Primary team:** **Platform Engineering** — owns the platform repos end to end
  and runs the bug-solving squad.
- **Reports up to:** Tech Lead **Omar Haddad**, then CTO **Nadia Brandt**; Sev-1
  incidents escalate CTO → CEO.
- **Serves every other division:** a bug reported from a branch counter, a customer
  channel, or monitoring lands here regardless of where it surfaced — Platform
  Engineering owns the code path that fixes it.

## Why this binding matters
Anchoring the base to the Platform Engineering roles means each squad member
inherits a real owner, expertise, and decision boundary: the `backend` agent
behaves like Raj (services & pricing logic), the `frontend` agent like Lena (UI),
the `tester` like Yuki (the failing-test gate), all led by Omar. Change a role
file in `company/`, and the squad member that mirrors it changes with it.
