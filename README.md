# PeakGuard

Interactive web app for the Palindromic Square Cliff.

PeakGuard is a local-first PWA for exploring when squaring a number in base `2..36` preserves palindromic structure and when carry propagation breaks the mirror. It combines exact and preview computation, carry animation, gallery examples, export and share tools, and local project persistence in one self-contained app.

No backend. No telemetry. Works offline after assets are cached.

![PeakGuard home](./evidence/screenshots/guide-01-home-desktop.png)

## Highlights

- Exact and preview square computation for custom roots and canonical repunits
- Convolution and carry visualizations, including a step-through animator
- Guidance panel for viable sparse families vs finite-ceiling families
- Local-only persistence with export to JSON, Markdown, SVG, PNG, and share URLs
- Installable PWA with offline support

## Quick Start

```bash
pnpm install
pnpm dev
```

Build the production bundle:

```bash
pnpm build
pnpm preview
```

Run the local verification set:

```bash
pnpm verify:local
```

Run the full release gate:

```bash
pnpm verify
```

## Documentation

- [USER_GUIDE.md](./USER_GUIDE.md) for the product walkthrough
- [docs/MATH.md](./docs/MATH.md) for the implementation math and theorem details
- [docs/TECH_SPEC.md](./docs/TECH_SPEC.md) for the app contract and architecture
- [docs/APP_STORY.md](./docs/APP_STORY.md) for product framing
- [docs/USER_STORY.md](./docs/USER_STORY.md) for acceptance framing

## Core Claim

For repunits in bases `b >= 3`, the last palindromic repunit square occurs at length `n = b - 1`. At `n = b`, the central convolution coefficient reaches the radix, carry propagation begins, and the palindromic structure breaks. Base 2 is the special case: `11_2^2 = 1001_2` is still palindromic, while `111_2^2 = 110001_2` is not.

PeakGuard turns that phase transition into an interactive workflow: build a root, inspect the raw coefficients, step through carries, and export the result.

## Repository Notes

- Product name: `PeakGuard`
- Research theme: `Palindromic Square Cliff`
- Stack: React, TypeScript, Vite, Dexie, Comlink, Playwright, Vitest
- Generated build output and test evidence are intentionally not tracked
