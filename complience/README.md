# Complience

The **complience** folder captures the laws and regulations DriveEasy must satisfy and
turns them into checks agents apply during the rental lifecycle. Where `security/`
protects the data, `complience/` proves the business follows the rules. A violation
blocks the relevant `conductor` workflow gate.

## Compliance areas (DriveEasy)
- **Rental-agreement law** — every reservation produces a valid, jurisdiction-correct
  contract before pickup; terms (mileage, fuel, liability) are disclosed.
- **Insurance regulations** — coverage options are offered and recorded; claims route
  through the insurance partner before billing.
- **Driver's-license verification** — license validity, age, and class are confirmed
  for the vehicle being rented (luxury and van classes carry stricter checks).
- **Data privacy (GDPR / CCPA)** — honor access, export, and deletion requests for
  customer data; retention limits on telematics and rental history.

## How it's applied
Compliance checks are `QualityGates` (see `principales/`) wired into the lifecycle: no
pickup without a valid contract and verified license, no invoice without a cleared
inspection. Audit trails are kept for regulators.
