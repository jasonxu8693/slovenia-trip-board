# Slovenia Crew Trip Board

A live, gamified, group-facing planning board for the **Slovenia crew trip — Ljubljana · Bled · Julian Alps, 11–15 Sep 2026**.

Single self-contained `index.html` (inline CSS/JS, no build step), hosted free on **GitHub Pages**, with optional **live Google Sheets sync** so the whole crew shares one board state (votes, group bosses, personal checkpoints, roster & vibes).

## Live URL

https://jasonxu8693.github.io/slovenia-trip-board/

## What it does

- **Board** — a Slovenia alpine quest map (Lake Bled island church, Bled castle, Triglav peaks, Ljubljana dragon, cable-car gondolas, kozolec hayrack). Each traveller's token moves along the route as they clear checkpoints.
- **Activity Market** — vote keen / maybe / no on caves, gorges, cable cars and lake days; live tally meters and shortlist status.
- **Group tasks** — the shared "bosses": route, budget, cave call, accommodation, cars, activities, dinners, launch pack.
- **Personal checkpoints** — each person's own journey (flights, votes, shares, admin, packed).
- **Roster & vibes** — rename travellers, set roles, pick a personal vibe.
- **Countdown** to Ljubljana, confetti on group-boss completion, copy-summary buttons.

## Live sync (Google Sheets)

Sync is optional and off until wired:

1. New Google Sheet → name it `Slovenia Crew Trip Board Sync`.
2. Extensions → Apps Script → paste `apps-script/Code.gs` → Save.
3. Run `setup` once (authorise).
4. Deploy → New deployment → Web app → **Execute as: Me**, **Who has access: Anyone** → Deploy.
5. Copy the `/exec` URL and paste it into `const REMOTE_API_URL = "…"` near the top of the `<script>` in `index.html`.
6. Commit & push — Pages redeploys in ~1 min and the **Live** chip lights up.

Sync is whole-state, last-write-wins (fine for a small crew). Tap the **Live** chip to pull others' changes; it also auto-polls every 25s.

## Edit & redeploy

Change `index.html`, then:

```bash
git add -A && git commit -m "Update board" && git push origin main
```

GitHub Pages rebuilds in about a minute.
