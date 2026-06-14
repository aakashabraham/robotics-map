# FTC Premier Istanbul 2025 · World Teams Map

An interactive, futuristic world map visualizing all competing teams at **FTC Premier Istanbul 2025** — the largest FTC event in Europe. Built as a single HTML file with no build step required.

**Live site:** https://aakashabraham.github.io/robotics-map/

---

## Features

- **Interactive map** — dark-themed Leaflet.js map with English labels and continent markers
- **Team popups** — click any pin to see team name, origin, division, live stats, and recent awards
- **Spotlight mode** — auto-cycles through all teams every 10 seconds, flying the map to each location
- **Live stats** — pulls NP OPR, world rank, auto/driver-control scores, and awards from the FTC Scout API in real time
- **Division badges** — teams are labeled Rumeli (gold) or Valens (purple) based on their division assignment
- **Flat country flags** — crisp rectangular flags via flagcdn.com for every team's country
- **Marker clustering** — nearby teams cluster together at lower zoom levels and expand on click
- **Search** — filter teams by name or number in the sidebar

## Tech Stack

| Layer | Library / Service |
|---|---|
| Map | [Leaflet.js](https://leafletjs.com/) 1.9.4 |
| Tiles | CartoDB Dark (no labels) + Esri World Dark Gray Reference |
| Clustering | [Leaflet.markercluster](https://github.com/Leaflet/Leaflet.markercluster) |
| Fonts | Orbitron, Exo 2 (Google Fonts) |
| Data | [FTC Scout GraphQL API](https://api.ftcscout.org/graphql) |
| Flags | [flagcdn.com](https://flagcdn.com/) |
| Hosting | GitHub Pages |

## Data Sources

All team and stats data is fetched live at page load from the FTC Scout API:

- **Event teams** — `eventByCode(season: 2025, code: "FPEIST")`
- **Rumeli Division** — `eventByCode(season: 2025, code: "FPEISTRDIV")`
- **Valens Division** — `eventByCode(season: 2025, code: "FPEISTVDIV")`
- **Team stats** — `teamByNumber` batched query for OPR, world rank, rookie year, school name, and awards

## Usage

Open `index.html` in any modern browser — no installation or build step needed.

```bash
open index.html
```

Or visit the live site linked above.

## Deployment

The site is deployed via GitHub Pages from the `main` branch. To update:

```bash
git add index.html
git commit -m "your message"
git push
```

GitHub Pages will rebuild automatically within ~60 seconds.

## About

Built for FTC Premier Istanbul 2025, an invitational FIRST Tech Challenge event held in Istanbul, Turkey. The event features teams from across the world competing in two divisions: Rumeli and Valens.
