# Global Health Risk Dashboard

An interactive, single-page dashboard that visualizes country-level health risk information on a map. Built as a personal frontend project to explore data visualization, live API integration, and client-side UI design.

**Live demo:** [khan34535-sudo.github.io/one-health-biosecurity](https://khan34535-sudo.github.io/one-health-biosecurity/)

## What this is

A frontend prototype, not a production surveillance tool. It's a portfolio piece demonstrating interactive map UI, real API integration, and structured data presentation.

## What it does

- **Interactive world map** (Leaflet.js) — click a country pin, use the A–Z index, or search by name to pull up its profile
- **Live WHO data** — fetches real, current life expectancy data for each country directly from the [WHO Global Health Observatory API](https://www.who.int/data/gho/info/gho-odata-api) (indicator `WHOSIS_000001`). No API key required; runs entirely client-side.
- **Static reference layers** — illustrative summaries of zoonotic, respiratory, fungal, STI, and venomous-species information per country, clearly labeled as static reference content, not live surveillance data
- **Adjustable risk score** — a simple weighted scoring demo that recalculates when you toggle risk-category checkboxes (illustrative math, not a validated epidemiological model)
- **QR code export** — generates a real, scannable QR code encoding the currently displayed risk snapshot as JSON. Nothing is stored; the data exists only in the browser session.

## Tech stack

- HTML5 / CSS3 (Tailwind CDN)
- Vanilla JavaScript
- [Leaflet.js](https://leafletjs.com/) for mapping
- [qrcode.js](https://davidshimjs.github.io/qrcodejs/) for QR generation
- [WHO GHO OData API](https://www.who.int/data/gho/info/gho-odata-api) for live data
- No backend, no build step, no dependencies beyond CDN scripts — deployable as a static site

## What this is NOT

To be upfront about scope:
- Not affiliated with, endorsed by, or sponsored by the WHO, any government, or any health agency
- Not a real-time outbreak surveillance system — the live data pulled is periodic WHO-reported statistics (life expectancy), not case-level outbreak tracking
- The disease/risk category summaries are illustrative reference text, not sourced from a live epidemiological feed
- The risk scoring formula is a simple demo weighting, not a validated clinical or epidemiological model

## Status

Personal project, actively maintained. Feedback and suggestions welcome via GitHub issues.

## License

© 2026 Asia Khan. All rights reserved. Viewing and personal review of this repository is permitted. No reproduction, redistribution, or commercial use without written permission — see [LICENSE.md](./LICENSE.md).
