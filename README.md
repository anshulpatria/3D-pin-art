# Pin Art 3D — Pinscreen Sculptor

A browser-based 3D **pinscreen / pin-art** toy, like the metal pin-impression boards — but in WebGL, with colour, glow, and image imprinting. Push pins with your cursor (or fingers on a touchscreen) to sculpt, or upload an image to imprint its depth into the board.

Built as a single self-contained `index.html` — no build step, no dependencies to install. Just open it.

![Pin Art 3D](preview.png)

## Features

- **Sculpt mode** — push pins by pressing/dragging on the board. Pressure-sensitive on Force Touch trackpads; multi-finger on touchscreens (every finger pushes pins at once, like the real toy).
- **Image imprint** — upload any image and its light/dark values push the pins into a relief.
- **Trackball camera** — orbit freely from any angle with no gimbal flip; lay the board flat and walk around it. Preset views: Front, Iso, Iso 2, Flat, Side.
- **Colour ramps** — Ice, Forest, Fire, Mono, Plasma, plus Grabient-inspired tricolour gradients (Juicy, Bloody, Lush, Cosmic). Per-pin colour mode so each pin shows its own depth colour.
- **Material & glow** — roughness, metalness, and a neon bloom glow with surface presets (plastic matte/gloss, metal, rough, neon).
- **Studio lighting** — adjustable key-light angle and power.
- **Undo / redo**, reset, and **PNG export**.

## Controls

| Action | Input |
| --- | --- |
| Orbit | Drag on empty space |
| Sculpt | Turn on Sculpt mode, then drag on the board |
| Zoom | Scroll / pinch |
| Pan | Right-drag |
| Undo / Redo | Cmd/Ctrl+Z / Shift+Cmd/Ctrl+Z |

> **Multi-touch note:** true multi-finger sculpting works on touchscreens/tablets. Laptop trackpads can't report individual finger positions (a browser/OS limitation), so they're single-point with pressure.

## Run locally

No server needed — just open the file:

```bash
open index.html        # macOS
# or double-click index.html
```

(Three.js and its bloom add-ons load from CDN, so you need an internet connection the first time.)

## Deploy to GitHub Pages

1. Create a new GitHub repository and push these files to it:
   ```bash
   git init
   git add .
   git commit -m "Pin Art 3D"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Select branch **main** and folder **/ (root)**, then **Save**.
5. After a minute, your site is live at `https://<your-username>.github.io/<your-repo>/`.

Because the file is named `index.html`, GitHub Pages serves it automatically at the root URL.

## Tech

- [Three.js](https://threejs.org/) r128 (WebGL) loaded from CDN
- `UnrealBloomPass` for the neon glow
- Vanilla HTML/CSS/JS — everything in one file

## License

MIT — see [LICENSE](LICENSE).
