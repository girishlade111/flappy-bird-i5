# Flappy Bird

A playable Flappy Bird clone rendered on HTML5 canvas, built with Next.js 15, React 19, and TypeScript — with sprite-based animation, synthesized sound effects, and mobile-responsive scaling.

## What it does

- **Classic gameplay** — tap/click/spacebar to flap, fly through pipe gaps, score increments per pipe cleared, game-over screen with score.
- **Canvas rendering** — 288×512 fixed game area, time-based physics (gravity, jump velocity) clamped by delta time so gameplay speed is consistent across refresh rates.
- **Sprites & sound** — bird wing-flap frames, day background, pipes, number score sprites, game-over/message screens; wing/point/hit sounds synthesized via Web Audio.
- **Mobile-friendly** — auto-scales to fill the screen while preserving aspect ratio; jump cooldown to prevent double-taps.

> Note: sprites and audio are loaded at runtime from remote Vercel Blob storage URLs. The game is client-side only — no backend, no login.

## Tech stack

- **Framework:** Next.js 15 (App Router), React 19, TypeScript
- **Styling:** Tailwind CSS 3.4, shadcn/ui + Radix UI primitives
- **Rendering:** HTML5 `<canvas>` 2D context, `requestAnimationFrame` game loop
- **Audio:** Web Audio API (`AudioContext`, decoded buffers)

## Quick start

Prerequisites: Node.js 18+ and npm (or pnpm/yarn).

```bash
npm install
npm run dev
```

Open http://localhost:3000 and click/tap (or press Space) to start flapping.

Production build (static export — no API routes or server actions):

```bash
npm run build   # outputs to ./out
```

Serve `./out` with any static file server, or deploy to GitHub Pages / any static host.

## Project structure

```
app/
  page.tsx        # renders the FlappyBird component
  layout.tsx      # root layout + theme provider
flappy-bird.tsx   # the whole game: state, physics, canvas render loop, audio
components/       # theme-provider
public/           # placeholder assets (game art is loaded remotely)
```

## Environment variables

None required.

## Deployment

Fully static — ships with `output: 'export'` in `next.config.mjs` and deploys to GitHub Pages as a project site. `basePath: '/flappy-bird-i5'` is set so assets resolve under the `https://girishlade111.github.io/flappy-bird-i5/` subpath. To deploy at a domain root (e.g. Vercel), remove the `basePath` line from `next.config.mjs` before building.

---

Built by Girish Lade — https://ladestack.in
