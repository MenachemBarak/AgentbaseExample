# Plugins

The **plugins** folder holds agentic capabilities DriveEasy installs from
marketplaces, organized as `plugins/<marketplace>/<plugin>/`. A plugin packages a
tool or skill an agent can call — kept here so capabilities are versioned and
auditable rather than hard-wired into a role.

Layout: `plugins/<marketplace>/<plugin>/`.

## Plugins (DriveEasy)
- **plugins/driveeasy-internal/pricing-advisor/** — wraps the pricing engine so a
  Rental Counter agent can quote dynamic rates by vehicle class and demand.
- **plugins/vision-market/photo-damage-detection/** — analyzes return-lot photos to
  flag dents and scratches, feeding the damage-review gate before a customer is
  charged.
- **plugins/maps-market/telematics-geofence/** — alerts when a vehicle leaves its
  permitted region using live GPS.

Plugins respect the same model policy as `harness/`: damage-detection results are
reasoned over by the frontier model, while geofence pings are handled cheaply.
