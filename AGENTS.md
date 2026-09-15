# AGENTS.md

## Overview

DART Ticket is a **pure static front-end** — a single `index.html` (inline CSS + JS), a service worker (`service-worker.js`), a PWA manifest, and icon assets. There is no backend, no build step, no package manager, and no external API. All state lives in `localStorage`.

## Running

```bash
docker compose -f docker-compose.base44.yml up -d --build
```

Serves the static files via nginx on **port 3000**. No dependencies to install, no migrations, no secrets required.

## Editing

Edits to `index.html` (or any static asset) are served immediately by nginx — just refresh the preview. Use `reload_preview` when a hard refresh is needed (e.g. service worker changes).

## Key files

- `index.html` — the entire app (UI, logic, styles)
- `service-worker.js` — offline caching (cache-first)
- `manifest.webmanifest` — PWA install metadata
