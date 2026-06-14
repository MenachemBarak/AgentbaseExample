# Booking Bug Squad — base_bug_solving

> Human-led AI agent team for fixing DriveEasy platform bugs.
> *"No bug is fixed until a test that failed before passes after."*

Mirrors the **Technology → Platform Engineering** team. Each member's charter is
derived from the matching `company/` role.

## Coordinator

| Name | Role | Notes |
|------|------|-------|
| Squad | Coordinator | Routes the bug, enforces handoffs and the failing-test gate. Generates no domain artifacts itself. |

## Members

| Name | Role | Mirrors company role | Charter | Status |
|------|------|----------------------|---------|--------|
| Lead | Lead | `role_tech-lead` (Omar Haddad) | `.squad/agents/lead/charter.md` | ✅ Active |
| Frontend | Frontend Engineer | `role_frontend-engineer` (Lena Fischer) | `.squad/agents/frontend/charter.md` | ✅ Active |
| Backend | Backend Engineer | `role_backend-engineer` (Raj Mehta) | `.squad/agents/backend/charter.md` | ✅ Active |
| Tester | Quality Owner | `role_qa-engineer` (Yuki Tanaka) | `.squad/agents/tester/charter.md` | ✅ Active |
| Scribe | Session Logger | `role_tech-lead` (Omar Haddad) | `.squad/agents/scribe/charter.md` | 📋 Silent |

## Repos under this squad
`booking-system` · `pricing-engine` · `counter-terminal` · `fleet-telematics`
(from `repos/repos.yaml`, internal group).

## Routing
Bug → **Lead** triages and casts → **Tester** writes a failing test → **Backend**
and/or **Frontend** fix their layer → **Tester** verifies (no regressions) →
**Lead** approves & ships → **Scribe** logs the decision.
