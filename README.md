# Dynamic Equilibrium — Particle Flow

An interactive particle visualization inspired by Shinichi Fukuoka's *Dynamic Equilibrium* (動的平衡). Particles flow across the screen and react to a human figure detected in real-time using AI body segmentation — becoming larger, slower, and more opaque on the body, revealing the silhouette through particle density alone.

## Live Demo

**[Try it here](https://iverson777.github.io/2026_yugop_dynamic/)**

Upload a video or image of a person and watch the particles reveal the figure.

## Features

- **AI Body Segmentation** — Real-time person detection using TensorFlow.js + MediaPipe
- **3 Particle Modes**
  - **Flow** — Particles drift left-to-right, slowing on the body
  - **Magnet** — Particles attract to the body with position-based collision physics (no overlapping)
  - **Rain** — Particles fall like rain, pooling on the silhouette
- **Upload Support** — Works with video (MP4, MOV, WebM) or images (JPG, PNG)
- **Adjustable Parameters** — Particle count, size, opacity, speed, and more
- **Runs entirely in the browser** — No server required, no data uploaded

## How It Works

1. User uploads a video or image containing a person
2. TensorFlow.js with MediaPipe Selfie Segmentation generates a body mask at ~15fps
3. Thousands of particles check the mask to determine if they are "on body"
4. On-body particles grow larger and more opaque; off-body particles stay small and faint
5. The collective behavior reveals the human silhouette through emergent density

## Tech Stack

- **TensorFlow.js** + **MediaPipe Selfie Segmentation** for real-time body detection
- **Canvas 2D** for particle rendering
- **Position-Based Dynamics** for Magnet mode collision resolution
- **Spatial Hashing** for O(n) collision detection
- Single HTML file, zero build step

## Usage

Open `index.html` in a modern browser, or serve it locally:

```bash
python3 -m http.server 8080
```

Then visit `http://localhost:8080`.

## License

MIT
