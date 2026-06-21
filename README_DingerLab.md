# DingerLab — Stadium Night (wired) v6.0

`index.html` is the Stadium Night front-end design, kept exactly as exported,
with a non-destructive **live-data bridge** added. The bridge reads your real
DingerLab data (server `/api/state` → `modelExports` / `boardSnapshots`, plus
same-origin `localStorage`) and hydrates the Dashboard KPIs and Top Star Plays
cards from the live model. If no live data is reachable, the representative
design is shown unchanged — the UI never breaks.

## Run / deploy
- Open `index.html` directly (works offline; shows representative data).
- Serve it from the same host as the Flask backend (`dingerlab_server.py`) so
  the bridge can read `/api/state` same-origin. Otherwise it falls back to
  `https://mlb-slate.onrender.com`.

## Backend (unchanged)
`dingerlab_server.py`, `streamlit_app.py`, `requirements.txt`,
`README_streamlit.md`, `login_wallpaper.png` are unchanged from the prior build.
