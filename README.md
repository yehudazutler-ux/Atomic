# Tamid — habit and learning tracker

A mobile-first habit tracker. Daily / weekly / monthly habits with two built-in rules: 80%+ completion and never miss two in a row. Also includes Shnayim Mikra (weekly parsha with aliyos check-offs) and Daily Learning (Gemara, Halacha, Mussar, Mishnayos, Nach, Machshava/Chassidus).

## Files

- `index.html` — the whole app (design and logic).
- `data/content.json` — everything the app shows that comes from spreadsheets: the habit list, the parsha schedule, and the daily learning schedule. The app loads it on every open.

## How it is updated

Habits and schedules are maintained in spreadsheets. To publish a change, the `/habit-tracker-update` skill rebuilds `data/content.json` from the spreadsheets and uploads it here. `index.html` is only re-uploaded when the app itself changes.

## Progress is never touched

Check-offs, custom habits, chosen emojis, skip days and personal-pace bookmarks are stored only in the browser on your device (localStorage). Updating the spreadsheets or this repo never changes them. Habits are linked by a permanent ID, so renaming, pausing or adding a habit in the spreadsheet keeps its history.

## Using it

- Add to Home Screen on iPhone (Safari: Share > Add to Home Screen) for a full-screen app.
- Settings: tap a habit to edit its emoji; mark skip days; "Check for updates now"; export your data as JSON or CSV.
- The app works offline using the last saved copy of the schedule.

Parsha schedule data generated from the Hebcal Leyning API, hebcal.com, CC BY 4.0.
