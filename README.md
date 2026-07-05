# Interactive Flower

A web recreation of the TouchDesigner "Interactive Flower" concept — a plant grown
from an **L-system** grammar that sways and blooms in response to your hand,
tracked through the webcam with **MediaPipe**.

## How it works

- **L-system** — the bouquet comes from the branching grammar
  `X -> F[+X][-X]`, expanded 4 times and drawn with turtle graphics on a
  `<canvas>`. Every leftover `X` is a branch tip that gets a glowing lotus
  flower (pre-rendered sprite). It grows from a seed over ~14 seconds.
- **Look** — glowing gold-orange lotus heads on neon-blue stems over a warm
  sunset gradient, with glassmorphism UI panels and live Grow / Bloom
  readouts.
- **Hand tracking** — click *Enable Hand Tracking* to load MediaPipe's
  HandLandmarker (from CDN, runs fully in the browser):
  - Move your hand **left / right** → wind blows through the plant
  - **Pinch** your thumb and index finger **open / closed** → flowers bloom / close
- **Mouse fallback** — without a camera, mouse X controls wind and mouse Y
  controls bloom.

## Run it

It is a single static file — no build step, no dependencies to install.

Open `index.html` in a browser, or serve the folder:

```
npx serve .
```

Note: hand tracking needs camera permission, which browsers only grant on
`localhost` or HTTPS (fine for shared hosting).
