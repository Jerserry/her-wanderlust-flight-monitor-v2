# Her Wanderlust Path Flight Monitor

A Malaysia-focused flight monitoring dashboard for round-trip routes departing from Kuala Lumpur (KUL) and Singapore (SIN), with MYR currency display.

## Current build
- Responsive pink dashboard UI
- Workspace navigation inspired by the panel structure of [dengmeiluan/ticket-monitoring](https://github.com/dengmeiluan/ticket-monitoring)
- 44 destination airports and 88 origin-destination route pairs (KUL + SIN)
- 11-airline allowlist
- Route directory search and region/origin filters
- Explicit demo labels: no live fare collection is connected yet

## Important data note
The current GitHub Pages frontend is a UI prototype. It does **not** collect live flight prices. Do not treat any illustrative chart or UI element as a real quote. Live monitoring requires a lawful, reliable fare-data source and a backend/scheduled collector.

## Run locally
Serve this folder with any static web server (for example, `python3 -m http.server 8000`) and open `http://localhost:8000`.

## Reference and attribution
The interface structure is informed by the open-source project [ticket-monitoring](https://github.com/dengmeiluan/ticket-monitoring), licensed under Apache License 2.0. This repository is an independent adaptation for KUL/SIN routes, MYR display and a different airline/destination configuration. See [LICENSE](LICENSE). Original project authors retain their respective rights.

## Planned next steps
1. Validate the route and airline configuration.
2. Select and test a real international fare data source.
3. Add scheduled collection, storage, history and notifications.
4. Connect the dashboard to verified collected data.
