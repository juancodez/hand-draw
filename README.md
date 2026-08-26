# Hand Draw

Draw in the air with your hand — no mouse, no touch, just your webcam and MediaPipe.

![Hand Draw](https://img.shields.io/badge/built%20with-MediaPipe-blue) ![Vanilla JS](https://img.shields.io/badge/vanilla-JS-yellow) ![Single file](https://img.shields.io/badge/single-file-green)

## What it does

Your webcam feed becomes a canvas. Raise fingers to draw, close your fist to erase. No installation, no backend — one HTML file.

- **Draw mode** — index finger up traces glowing strokes on the canvas
- **Erase mode** — close your fist to scrub strokes with a soft circular eraser
- **Live cursor** — a glowing dot follows your fingertip in real time
- **Camera ghost** — your mirrored feed sits beneath the canvas at 25% opacity so you can see your hand position

## How it works

| Layer | Tech |
|---|---|
| Hand tracking | [MediaPipe Hands](https://google.github.io/mediapipe/solutions/hands) |
| Rendering | HTML5 Canvas API |
| Camera | `getUserMedia` |
| Everything else | Vanilla JS, zero dependencies |

MediaPipe detects 21 hand landmarks per frame. The app reads the index fingertip (landmark 8) and counts how many fingers are extended to switch between draw and erase modes.

## Run it

```bash
# Option 1 — just open it
open index.html

# Option 2 — serve locally (avoids some browser camera quirks)
npx serve .
# or
python -m http.server
```

Allow camera access when prompted. Point your hand at the camera and start drawing.

## Controls

| Gesture | Action |
|---|---|
| Index finger up | Draw |
| Fist / all fingers down | Erase |
| Move hand off screen | Pause |

## Built by

Juan Gomez-Vara — [juangomezvara.com](https://juangomezvara.com)
