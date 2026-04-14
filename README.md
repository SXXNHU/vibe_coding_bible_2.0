# Vibe Coding Tracks

## Overview

Vibe Coding Tracks is a Korean-language onboarding guide for development club newcomers entering AI-assisted development ("vibe coding"). The site explains what vibe coding is, how the describe-generate-verify loop works, and helps each reader select the learning track that fits their current tools and confidence level.

It exists because newcomers to AI-assisted development face a sharp choice problem: the right starting point depends heavily on whether they are using free chat-based AI, a paid AI editor, or a terminal-first CLI workflow. A single generic tutorial fails all three groups. This guide solves that by routing people upfront.

The primary audience is first-year members ("아기사자") of a university development club with no assumed prior coding experience.

---

## Features

- Three distinct learning tracks — Free, Paid, and CLI — each with its own dedicated guide page
- Track comparison table summarizing tools, workflow style, difficulty, and recommended audience
- Fully responsive layout that reflows from a three-column grid to a single column on mobile
- Dark and light theme with `localStorage` persistence and a first-visit tooltip prompt
- Social sharing metadata (Open Graph + Twitter Card) with a custom OG image
- Zero runtime dependencies in the delivered HTML — no framework bundle on the static pages

---

## Tech Stack

**Frontend**
- React 19 + TypeScript (Vite project scaffold, used for local development)
- Vite 8 — dev server, HMR, and production build

**Static pages (content)**
- Vanilla HTML/CSS with CSS custom properties for theming
- Google Fonts: Noto Sans KR, JetBrains Mono, Bebas Neue

**Tooling**
- ESLint 9 with `typescript-eslint` and `eslint-plugin-react-hooks`
- TypeScript 6

---

## Architecture

The project separates content from the scaffold:

- `public/` holds the finished static HTML pages. Each track guide (`vibe-coding-free.html`, `vibe-coding-paid.html`, `vibe-coding-cli.html`) and the landing index (`index.html`) are self-contained files with inlined CSS and a small inline script for theme handling. They are served directly without a build step.
- `src/` contains the Vite + React application used during development and for future interactive components. `src/App.tsx` currently renders a development landing that links out to the static pages.
- `dist/` is the Vite build output, which copies `public/` verbatim and compiles the React app alongside it.

This means the core content ships as plain HTML and works without JavaScript enabled, while the React layer is available for future interactivity.

---

## Getting Started

### Prerequisites

- Node.js 18 or later
- npm 9 or later

### Installation

```bash
git clone https://github.com/your-username/vibe-coding-tracks.git
cd vibe-coding-tracks
npm install
```

### Running the Project

```bash
npm run dev
```

The dev server starts at `http://localhost:5173`. Open `http://localhost:5173/index.html` to view the landing page, or navigate directly to any track:

| Path | Content |
|---|---|
| `/index.html` | Track selector landing page |
| `/vibe-coding-free.html` | Track 01 — Free User guide |
| `/vibe-coding-paid.html` | Track 02 — Paid User guide |
| `/vibe-coding-cli.html` | Track 03 — CLI User guide |

---

## Usage

The site is a read-once onboarding flow. A new club member lands on the index page, reads the vibe coding overview, and selects one of three tracks based on the comparison table.

**Typical flow:**

1. Reader lands on the index and reads the "describe → generate → verify" loop explanation.
2. They scan the three-column track cards and the comparison table to identify their setup.
3. They click into their track (Free, Paid, or CLI) and follow the guide for that environment.

**Theme:** The toggle in the top-right corner switches between dark (default) and light mode. The preference is stored in `localStorage` under the key `vibe-theme` and restored on next visit.

---

## Project Structure

```
vibe-coding-tracks/
├── public/
│   ├── index.html               # Main landing page (track selector)
│   ├── vibe-coding-free.html    # Track 01: Free User guide
│   ├── vibe-coding-paid.html    # Track 02: Paid User guide
│   ├── vibe-coding-cli.html     # Track 03: CLI User guide
│   ├── vibe-coding-index.html   # Alternate index entry point
│   ├── og-image.png             # Open Graph social preview image
│   ├── og-image.html            # Source file used to generate the OG image
│   ├── favicon.svg              # Site favicon
│   └── icons.svg                # SVG sprite (documentation, social, github icons)
├── src/
│   ├── App.tsx                  # React app entry (development scaffold)
│   ├── App.css                  # App-level styles
│   ├── main.tsx                 # React DOM mount point
│   ├── index.css                # Global reset/base styles
│   └── assets/                  # Static assets imported by the React app
├── index.html                   # Vite HTML entry (React app shell)
├── vite.config.ts
├── tsconfig.json
├── tsconfig.app.json
├── tsconfig.node.json
├── eslint.config.js
└── package.json
```

---

## Deployment

The site deploys as static files. Any static host works.

**Vercel**

```bash
npm run build
# Push to GitHub and connect the repo in the Vercel dashboard.
# Build command: npm run build
# Output directory: dist
```

**Manual / any static host**

```bash
npm run build
# Upload the contents of dist/ to your host.
```

The `dist/` directory contains everything needed: the compiled React app and all static HTML pages copied from `public/`.

---

## Roadmap / Future Work

- Interactive quiz to route users to the correct track automatically based on a few questions
- English translation of all guide pages
- Progress tracking per track (mark sections as read, stored in `localStorage`)
- Searchable FAQ section for common questions from each track
- Accessibility audit and ARIA improvements across the static pages

---

## Contributing

Contributions are welcome, especially corrections or additions to the guide content.

1. Fork the repository and create a branch from `main`.
2. Make your changes. If editing a static HTML guide, keep styles and scripts inline to preserve the self-contained structure.
3. Run `npm run lint` and confirm there are no errors.
4. Open a pull request with a clear description of what changed and why.

Content edits (typos, clarity, updated tool recommendations) are the most valuable contributions and do not require a development environment — the HTML files can be edited directly.

---

## License

MIT License. See `LICENSE` for details.
