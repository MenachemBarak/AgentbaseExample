# squad

**squad** is "human-led AI agent teams for any project." It is a CLI that works
with GitHub Copilot to give a single developer a coordinated set of specialist
agents — lead, frontend, backend, tester, scribe — that live as files in the
repository, each in its own context, with their knowledge tracked in git. squad
supports parallel execution, decision logging, and a 'Ralph' watch mode that
auto-triages incoming issues. One person leads; the agents do the specialized
work.

**Category:** `agentic_teams`

https://github.com/bradygaster/squad

## How DriveEasy uses it
When the **Metro Airport Branch** takes on a software/ops project — for example,
a new **self-service rental kiosk** — DriveEasy spins up a squad that *mirrors
the branch's own roles*, built directly on top of the `company/` role
definitions. The branch manager leads the squad exactly as she leads the branch.

| squad agent | Metro Airport Branch role | Holder |
|---|---|---|
| lead | `role_branch-manager` | Aisha Khan |
| frontend engineer | `role_rental-agent` | Diego Alvarez |
| backend engineer | `role_rental-agent` | Rental Sales Agent (Diego's peer) |
| tester | booking QA (`role_rental-associate`) | Ben Foster |
| scribe | shift-log (`role_counter-lead`) | Grace Liu |

The squad-lead (Aisha Khan) sets direction and approves merges; the rental
agents build the kiosk's customer-facing and booking-integration code; Ben
Foster validates the flow against the booking system; and Grace Liu keeps the
shift-log of decisions in git — the same shift discipline her counter already
runs on. When the kiosk project ships, the squad is archived and everyone goes
back to the counter.
