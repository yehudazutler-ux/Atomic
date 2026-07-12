# Cadence — habit tracker

A mobile-first, iOS-style habit tracker. Tracks daily / weekly / monthly habits
with two success rules built in: **80%+ completion** and **never miss two in a
row**. All data lives in `localStorage` on the device. Works fully offline.

## Files

```
.
└── index.html   ← the entire app (HTML + CSS + JS, no dependencies, no build step)
```

## Run locally

Just open `index.html` in a browser, or serve the folder:

```bash
npx serve .
```

## Deploy with GitHub Pages (free)

1. Create a new **public** repo on GitHub (e.g. `cadence`).
2. Upload `index.html` (and this `README.md` if you like) via "Add file" → "Upload files."
3. Repo → Settings → Pages → under "Build and deployment," set Source to
   "Deploy from a branch," Branch `main`, folder `/ (root)` → Save.
4. Wait ~30–60 seconds, refresh the Pages settings screen for your live URL
   (`https://yourusername.github.io/cadence/`).
5. To update later: edit `index.html` in the repo (pencil icon) and commit —
   Pages redeploys automatically.

## Add to Home Screen (native feel)
On iPhone: open the deployed URL in Safari → Share → "Add to Home Screen."
It launches full-screen with no browser chrome, respecting safe-area insets.

## Shnayim Mikra

A dedicated tab shows the current week's parsha with all seven aliyos (verse ranges
included) and five check-offs per aliyah — Mikra, Mikra, Targum, Rashi, Ramban (35 total).
Arrows move between weeks; "Jump to this week" returns to today. The parsha schedule for
2026-07-11 through 2028-12-30 (Diaspora, full kriyah) is embedded, so it works offline.

Schedule data generated from the Hebcal Leyning API, hebcal.com, CC BY 4.0.

## Daily Learning

A dedicated "Learn" tab shows each day's assignments from your personal Torah Calendar
spreadsheet — Gemara, Halacha, Mussar, Mishnayos, Nach, and Machshava/Chassidus — with a
check-off per subject (subjects with nothing scheduled that day are hidden). Arrows move
between days; "Jump to today" returns to the current date.

Calendar year 2026 (Jan 1 – Dec 31) is embedded from the "Torah Calendar.xlsx" spreadsheet,
so it works offline. As the spreadsheet is extended into 2027 and beyond, re-embed the next
year's rows into the `DAILY` array near the top of the `<script>` block in `index.html`
(same format: `["YYYY-MM-DD", Gemara, Halacha, Mussar, Mishnayos, Nach, Machshava]`, empty
string for any subject not scheduled that day).

## Data
- **Persist:** automatic, in `localStorage` (`cadence.v1`).
- **Export JSON / CSV:** Settings tab. The habit CSV is one row per period
  (`Habit, Cadence, Period, Start Date, Completed`) — ready to pivot in Excel.
  The Shnayim Mikra CSV mirrors the original spreadsheet layout (Week Ending, Parsha,
  then 7 aliyos x 5 columns). The Daily Learning CSV mirrors the Torah Calendar
  spreadsheet layout (Date, then one column + a Done flag per subject).
