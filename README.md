# Chronos Flow

A mobile-first, single-file time-management web app for auditing how you spend your day. Log tasks onto a timeline, categorize them, and get an instant "time audit report" with an ROI metric and an efficiency rating.

> The UI is currently in Chinese (Simplified).

## Features

- **Daily timeline** — Plan and log tasks across a 09:00–01:00 window with collapsible time blocks.
- **Activity categories** — Tag each block as work, study, play, fitness, or other.
- **Fixed routines** — Built-in slots for morning prep, lunch, dinner, and evening rest.
- **Wasted / fragment gaps** — Mark idle or fragmented time so it shows up in your report.
- **Time audit report** — See an ROI metric `(work + study hours) / total committed time` and an overall efficiency rating.
- **Live clock & countdown** — Current time plus remaining hours in the day.
- **Per-date persistence** — Tasks are saved in the browser's `localStorage` under keys like `chronos_tasks_YYYY-MM-DD`. No account or backend required.

## Getting Started

No build step is required — the entire app lives in `index.html`.

### Option 1: Open directly

Clone the repo and open the file in your browser:

```bash
git clone https://github.com/wuyuyang001-oss/chronos-flow.git
cd chronos-flow
open index.html   # macOS — or just double-click the file
```

### Option 2: Serve locally

Some browsers restrict features on the `file://` protocol, so serving over HTTP is recommended:

```bash
# Python 3
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Usage

1. Open the app and confirm the date at the top.
2. Add tasks to the timeline and assign each a category.
3. Mark fixed routines and any wasted/fragment gaps.
4. Review the generated time audit report (ROI and efficiency rating) at the bottom.

Your data stays in the browser. Switching dates loads that day's saved tasks; clearing browser storage erases them.

## Tech Stack

- **React 18** (via CDN)
- **Babel Standalone** — in-browser JSX transpilation
- **Tailwind CSS** (via CDN)
- **Lucide** icons
- **localStorage** for persistence

> **Note:** Runtime dependencies are currently loaded from CDNs without pinned versions (Lucide uses `@latest`), and JSX is transpiled in the browser via Babel Standalone. This keeps the project zero-build but is not production-grade — pinning versions and precompiling are recommended before any production use.

## Roadmap / Ideas

- Pin CDN versions or add a real build step (Vite) and precompile JSX.
- Add an English locale / i18n.
- Export and import audit data.

## License

Released under the [MIT License](LICENSE).
