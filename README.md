# aerograph
AEROGRAPH — write math in the air ✋🧮 A hand-tracking calculator that reads digits/operators drawn with your index finger (MediaPipe), converts them to text via Tesseract.js OCR, and solves them instantly with math.js. Includes touch fallback, practice mode, and live stats — 100% client-side, no backend, no data uploaded.

# AEROGRAPH — Air Calculator ✋🧮

Write math in the air with your index finger. AEROGRAPH tracks your hand using **MediaPipe Hands**, reads what you drew with **Tesseract.js OCR**, and evaluates it with **math.js** — all running fully client-side, nothing recorded or uploaded.

🔗 **Live demo:** `https://<your-username>.github.io/<repo-name>/`

## Features

- ✋ **Hand-tracking drawing** — index finger up = draw, index+middle = pen up/move, open palm held = clear canvas
- 👆 **Touch/mouse fallback** — works even without camera access (tap & drag to draw, 2-finger tap to undo)
- 🔤 **Handwriting → math OCR** — Tesseract reads your air-written digits/operators, cleans them up, and feeds them to math.js
- 🧮 **Free Calc mode** — edit the recognized expression before executing
- 🎯 **Train mode** — timed practice questions with streaks, solve count, and per-question timing
- 📊 **Stats dashboard** — total drawn, correct answers, best streak, average solve time, chart of recent solve times (Chart.js)
- 🎨 **Drawing tools** — 6 stroke colors, adjustable stroke width, undo, save canvas as PNG
- 📱 **Mobile-first** — bottom nav bar, responsive layout, works as a home-screen web app

## Tech Stack

| Library | Purpose |
|---|---|
| [MediaPipe Hands](https://developers.google.com/mediapipe) | Real-time hand landmark tracking |
| [Tesseract.js](https://tesseract.projectnaptha.com/) | In-browser OCR |
| [math.js](https://mathjs.org/) | Safe expression evaluation |
| [Chart.js](https://www.chartjs.org/) | Stats visualization |

No build step, no backend, no dependencies to install — it's a single `index.html` file that pulls libraries from CDN.

## Run Locally

Just open `index.html` in a browser, or serve it locally:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

> Camera access needs a secure context (`https://` or `localhost`) — plain `file://` won't work for hand-tracking, but touch mode always works.

## Deploy to GitHub Pages

1. Create a new repo (e.g. `aerograph`) and push this file:
   ```bash
   git init
   git add index.html README.md
   git commit -m "AEROGRAPH: air-written math calculator"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
2. Go to **Settings → Pages** on GitHub
3. Under **Source**, select `main` branch, `/ (root)` folder → **Save**
4. Your live link will be `https://<your-username>.github.io/<repo-name>/`

## Notes

- Camera is blocked in some in-app browsers (Instagram/LinkedIn preview, etc.) — open in Chrome/Safari directly, or use the built-in **USE_TOUCH_INSTEAD** fallback.
- Nothing is uploaded anywhere — hand-tracking, OCR, and math evaluation all happen locally in the browser.

---
Built by Anshu Kumar
