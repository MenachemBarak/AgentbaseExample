# Roles — Platform Engineering

## Role hierarchy
Four roles run platform delivery, led by the Tech Lead:

- **role_tech-lead** — **Omar Haddad**, Tech Lead. Owns the team's work, sequences
  the bugs and features, and leads the bug-solving squad. Reports to CTO Nadia Brandt.
- **role_frontend-engineer** — front-end engineer (exemplar **Lena Fischer**). Owns
  the customer- and counter-facing UI in `booking-system` and `counter-terminal`.
- **role_backend-engineer** — back-end engineer (exemplar **Raj Mehta**). Owns the
  services and data in `booking-system` and `pricing-engine`.
- **role_qa-engineer** — QA engineer (exemplar **Yuki Tanaka**). Reproduces bugs,
  writes the failing test, and verifies the fix before release.

The Tech Lead sits above the three engineers; all four report up to the CTO.

- [roles/role_tech-lead.md](roles/role_tech-lead.md)
- [roles/role_frontend-engineer.md](roles/role_frontend-engineer.md)
- [roles/role_backend-engineer.md](roles/role_backend-engineer.md)
- [roles/role_qa-engineer.md](roles/role_qa-engineer.md)

## Collaboration & communication
- **Bug intake:** a bug reported from a branch counter, a customer, or monitoring
  lands with the Tech Lead, who scopes it and assigns an owner.
- **The squad:** for anything non-trivial, Omar runs the **bug-solving squad**
  (`agentic_bridge/driveeasy_bridge/bridge/bug-solving/`) — the squad's lead /
  frontend / backend / tester / scribe agents are these four roles.
- **Verification gate:** no fix ships until the QA engineer's failing test passes
  in `environments/`; the Tech Lead approves the release.
- **Escalation:** Sev-1 incidents go Tech Lead -> CTO -> CEO.
