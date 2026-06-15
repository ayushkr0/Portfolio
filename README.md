# The Desk — Ayush Kumar's Portfolio

An interactive 3D portfolio in a single HTML file. A desk with three screens and a phone — click any of them to fly into that section.

**Try it:** open `index.html` via any static server (e.g. `python3 -m http.server`) — no build step, no dependencies to install. Three.js loads from a CDN.

## What's on the desk

- **Main monitor** → projects (and it doubles as a Breakout screen — click the PS5 controller, arrow keys to play)
- **Vertical monitor** → about me
- **Laptop** → contact
- **Phone** → resume download
- **Lamp** → pull the chain (verlet rope physics) to switch day/night; the whole UI re-themes
- Live local-time clock on the wall and in the monitor's terminal strip, typing-sound ambience, drag to peek around the desk

Phones get a lightweight 2D fallback — the 3D scene never initializes on small screens.

## Stack

Three.js (WebGL), vanilla JS, CSS — one file, no framework, no build. Every prop is hand-built from primitives, and screen contents are canvas-drawn textures.
