# Money Diary

A personal diary, work-task list and money tracker that works **without internet** and syncs between your phone and computer.

- Diary notes with mood, expenses (with receipt photos), income and monthly budgets
- Work tasks with instructions, where to process them, urgent requests and a copyable work report
- Monthly bills, money to collect from people (e.g. internet you share), IOUs and savings goals
- A calculator on every amount, plus spending and 5 PM work reminders inside the app

## How it works

- `index.html` is the whole app. Everything you add is saved on the device first (IndexedDB), so it works offline.
- `sw.js` is a service worker that keeps the app files on the device, so the app opens with no internet after the first visit.
- When you're online, changes sync to a private Supabase table (`public.items`). Row Level Security means each account can only read and change its own rows.
- The Supabase URL and publishable key in `index.html` are meant to be public. Your data is protected by your login and the database rules, not by hiding the key.

## Install on your phone

1. Open the site once with internet and sign in.
2. **iPhone (Safari):** Share → **Add to Home Screen**. **Android (Chrome):** ⋮ → **Install app** (or **Add to Home screen**).
3. Open Money Diary from the home-screen icon. It now works offline.

## Updating

Change the files, bump `VERSION` in `sw.js` (e.g. `md-v2`) so phones pick up the new version, and push to `main`. GitHub Pages redeploys automatically.
