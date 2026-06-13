# Security

The **security** folder defines how DriveEasy's agents handle sensitive data and the
tooling that enforces it. These rules are mandatory for every role and are referenced
by `principales/` (Security, Permissions) and by `complience/`.

## Concerns (DriveEasy)
- **Payment / PCI data** — card details are tokenized by the booking system; agents
  see tokens, never raw PANs. No card data in logs, prompts, or `headroom` caches.
- **Customer PII** — names, addresses, and contact info are minimized and masked in
  agent context; access is scoped to the branch serving the rental.
- **Driver's-license handling** — license images and numbers are encrypted at rest
  and used only for the verification step, then access is revoked.
- **Fraud detection** — flags stolen-card patterns, identity mismatches, and
  geofence-violating vehicles (see `plugins/`), routing hits to the Escalation
  principle.

## Tooling
Secret management for booking-system and pricing-engine credentials, redaction of
tool outputs before they reach the model, and audit logging of every production write
recorded against the acting role.
