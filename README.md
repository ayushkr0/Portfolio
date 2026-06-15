# The Desk

An interactive 3D portfolio that lives on a workstation. Instead of scrolling a page, you walk up to a desk, click the monitors to read about my work, pull the lamp's chain to flip the room into night mode, and — if you're procrastinating — grab the controller and play Breakout on the main screen.

**Live:** https://ayushkr0.github.io/portfolio/

> Built as one HTML file. No framework, no build step, no bundler. Open it and it runs.

---

## What you can do

- **Click any screen to dive in.** The three monitors and the phone are each a section — projects, about, contact, and a downloadable résumé. Click one and the camera flies into it; the screen becomes the page.
- **Pull the lamp chain for night mode.** The chain is a real verlet-physics rope — it sways and yanks when you click it, plays a switch sound, and fades the whole room (and the UI) from day to night. After 7pm your local time, it starts dark on its own.
- **Play the controller.** The DualSense on its stand launches a full game of Breakout on the main monitor. Arrow keys to move, and the screen really is the playfield.
- **Look around.** Drag anywhere to peek around the desk. The monitors run a live clock on your local time, the keyboard clicks in sync with the code typing itself on screen, and the wall clock actually tells the time.

On phones, the 3D scene steps aside and the same content renders as a clean, fast, scrollable page — so it loads instantly and reads well on any device.

## How it's built

Everything you see is hand-built geometry — the desk, the mechanical keyboard down to individual keycaps, the lamp, the plants, the books. There are no downloaded 3D models. Each monitor's contents are drawn to a `<canvas>` and mapped onto the screen as a texture, which is why flying into a section feels like the screen turning into the page.

| | |
|---|---|
| **Rendering** | [Three.js](https://threejs.org/) `0.170` (WebGL), PBR materials, image-based lighting, soft shadows |
| **Code** | Vanilla JavaScript (ES modules), CSS — a single `index.html` |
| **Audio** | Web Audio API — synthesized keystrokes and the lamp switch, no audio files |
| **Physics** | A small verlet integrator for the lamp's pull chain |
| **Hosting** | Static — GitHub Pages. Three.js loads from a CDN; nothing to install |

A few details I'm quietly proud of: the boot-up screen flicker on load, day/night cross-fading every light and material in the scene at once, the typing audio locked to the on-screen code, and a graceful fallback to a plain page if a visitor's browser can't do WebGL — no one gets a blank screen.

## Running it locally

It needs a static server (opening the file directly breaks ES-module imports):

```bash
# from the project folder
python3 -m http.server 4173
# then open http://localhost:4173
```

Or in VS Code, right-click `index.html` → **Open with Live Server**.

## Project structure

```
index.html          the entire site — scene, sections, game, styles
Ayush jp Resume.pdf  résumé, served by the phone's download button
README.md
```

## About

Built by **Ayush Kumar** — GenAI engineer and MSc Advanced Computer Science student at the University of Sheffield.

- Email · [ayuxh.cs@gmail.com](mailto:ayuxh.cs@gmail.com)
- GitHub · [@ayushkr0](https://github.com/ayushkr0)
- LinkedIn · [/in/ayuxh](https://linkedin.com/in/ayuxh)
