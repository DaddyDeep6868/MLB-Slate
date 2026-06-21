# DingerLab v6.2 — Stadium Night (real working app)

A full rebuild: the Stadium Night design as a genuinely interactive single-file
app. No dead mockup — the nav works, buttons work, and there is a real
**Load today’s slate** button.

## What it does
- **Load today’s slate**: pulls today’s MLB games from the public MLB Stats API
  (schedule, probable pitchers, venues) and each team’s top power hitters with
  season stats.
- **Runs the model**: computes per-hitter HR probability + component scores
  (Power, Recent form, Pitcher matchup, Park/weather, Lineup spot, Odds value,
  Confidence) → a Dinger Score, with park factors and platoon handling.
- **Refresh odds**: pulls player-prop prices from your Flask backend
  `/api/oddsblaze`, computes EV and edge vs the model. No backend reachable =>
  the model still runs in **model-only mode**.
- **8 working tabs**: Dashboard, Games, Builder (parlay slip + Kelly staking),
  Data (model breakdown), Research (why-it-hits / risks), Tracking (ledger +
  ROI, synced to `/api/state`), Tools (settings), Live.
- Click any play to open the **Intelligence Report** drawer.

## Run
- Open `index.html` (needs internet for MLB data + fonts).
- Set your backend URL under **Tools** (defaults to `mlb-slate.onrender.com`).
  Odds need your OddsBlaze key set in the backend’s environment.

## Backend (unchanged)
`dingerlab_server.py`, `streamlit_app.py`, `requirements.txt`,
`README_streamlit.md`, `login_wallpaper.png` are unchanged.
