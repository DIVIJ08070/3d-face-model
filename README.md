# 3d-face-model

**FaceForge 3D** — scan your face from three angles with your webcam and turn it
into an interactive, textured 3D model you can view and download
(GLB / OBJ / STL / PNG). Runs **100% in your browser** — no server, no uploads,
your photos never leave your device. The entire app is one file: `index.html`.

## ▶ Run it

This is a **camera app**, so it must be served over **HTTPS** or
**http://localhost** — browsers block camera access on `file://`.

### Option A — GitHub Pages (easiest, gives you HTTPS)
1. On GitHub: **Settings → Pages**.
2. **Source:** *Deploy from a branch* → **Branch:** `main` → **/(root)** → **Save**.
3. Wait ~1 minute, then open: **https://divij08070.github.io/3d-face-model/**
4. Allow the camera when prompted.

### Option B — Local
```bash
python3 -m http.server 8000
# then open http://localhost:8000 and allow the camera
```

## 🧭 How to use
1. **Start Scan** → keep your face in the oval (front), then slowly turn **left**,
   then **right** — the angle gauge turns **green** when you're in the capture zone.
2. **Build 3D** → you get a **full head + shoulders bust**: textured face on the
   front, a skin-toned cranium behind (colour sampled from your photo), **ears**
   on both sides, and a **neck** stub. Rotate / zoom; toggle **Full head /
   Face-only**, wireframe, texture, auto-rotate, reset view, or the background.
   (Head shape/ears/neck are tunable via the `HEAD` constants in the source.)
3. **Download** as **GLB** (recommended — full head with texture embedded),
   **OBJ**, **STL** (full head, for 3D printing), or a **PNG** snapshot.

## 🛠 Tech
Vanilla JS · [Three.js](https://threejs.org) · MediaPipe Face Mesh (468 facial
landmarks) · Delaunay triangulation. All dependencies load from CDN.
Tested in current **Chrome, Edge, Safari**.

## ⚠ Note
This is a **landmark-based** reconstruction (a stylized 3D face), not
photogrammetry — great for a fun, downloadable 3D avatar, not a metrology-grade
scan. Face tracking and the turn-angle feel depend on lighting and your camera.
