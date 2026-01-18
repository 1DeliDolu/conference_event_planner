# Conference Event Planner

A modern, lightweight React + Vite web app for estimating conference and event costs. Users can pick venue rooms, add AV equipment, and choose meal options — totals update in real time. State is handled with Redux Toolkit.

---

## Overview

Conference Event Planner is a client-side UI that demonstrates a simple event cost estimation flow. The app separates concerns with Redux slices for venues, AV add-ons, and meals, and presents a clear interactive UI for selecting items and viewing subtotals and totals.

## Features

- Interactive venue selection with quantity controls
- AV add-ons (projector, speakers, microphones, whiteboards, signage) with per-item quantities
- Meal selection with configurable number of guests
- Live subtotal and overall total calculation
- State organized using Redux Toolkit slices (`venueSlice`, `avSlice`, `mealsSlice`)

## Tech stack

- JavaScript (ES modules) + React 18
- Vite (development server, fast rebuilds, production build)
- Redux Toolkit + React Redux for state management
- ESLint for linting

## Repository structure (key files)

```
.
├─ index.html
├─ package.json
├─ LICENSE
├─ src/
│  ├─ main.jsx           # App bootstrap (ReactDOM + Provider)
│  ├─ App.jsx            # Top-level UI and entry screen
│  ├─ ConferenceEvent.jsx# Main interactive UI (venue, add-ons, meals)
│  ├─ TotalCost.jsx      # Summary / totals view
│  ├─ store.js           # Redux store configuration
│  ├─ venueSlice.js      # Venue data + reducers
│  ├─ avSlice.js         # AV add-ons data + reducers
│  ├─ mealsSlice.js      # Meal options + reducers
  └─ assets/             # Static images
```

## Prerequisites

- Node.js + npm (project uses `package.json`)

## Quickstart

Install dependencies and run the development server:

```bash
npm install
npm run dev
```

Vite will print the local URL (usually `http://localhost:5173`). Open it in your browser.

## Local development

- Install dependencies: `npm install`
- Start dev server: `npm run dev`
- Build for production: `npm run build`
- Preview production build: `npm run preview` (runs `vite build` then `vite preview --host`)
- Lint: `npm run lint`

### Environment / configuration

This is a static client application. No `.env` or other runtime configuration files were detected in the repository. If you add integrations (APIs, analytics), include `.env.example` and document required variables here.

## Testing

No test framework or `test` npm script is present. To add tests, consider using Vitest or Jest and add a `test` script to `package.json`.

## Linting / Formatting

Run ESLint across the codebase with:

```bash
npm run lint
```

The lint script is defined in `package.json` as:
`eslint . --ext js,jsx --report-unused-disable-directives --max-warnings 0`.

## Docker

No Dockerfile or Docker Compose configuration was found. If you want a containerized dev/build environment, I can add a minimal `Dockerfile` and `docker-compose.yml`.

## CI/CD

No CI/CD workflows were found under `.github/workflows`. I can scaffold a GitHub Actions workflow for install, build, and lint if needed.

## API / Backend

This repository contains only a client application; there are no server endpoints or API integrations included.

## Troubleshooting

- If `npm run dev` fails, ensure your Node version is compatible and `npm install` completed without errors.
- If the port is in use, Vite will pick an alternative port; check the terminal output for the served URL.
- If images don't display, verify files in `src/assets/` or update the `img` paths in slice initialState objects.

## Contributing

- Open an issue to discuss larger changes.
- Fork, create a feature branch, and open a pull request with a clear description and tests where applicable.

## Security

No `SECURITY.md` was detected. For security issues, open an issue or contact maintainers directly.

## License

This project is licensed under the Apache License 2.0 — see the `LICENSE` file for details.

---

## Assumptions / TODO

- Tests: no test framework or `test` script found (checked `package.json` and `src/`).
- Env/config: no `.env` or config files found — app appears client-only.
- CI: no `.github/workflows` detected.
- Docker: no container config present.
- Contributing docs: `CONTRIBUTING.md` not present.

If you'd like, I can:

- add a minimal test setup (Vitest) and `npm test` script,
- create a `Dockerfile` and `docker-compose.yml` for local containerized development,
- scaffold a GitHub Actions workflow for install/build/lint,
- add a short `CONTRIBUTING.md` and `SECURITY.md`.
