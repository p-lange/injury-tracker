# ⚔️ Injury Tracker — Owlbear Rodeo Extension

Track per-token injuries with severity, complications, treatment status, and descriptions.

## Severity Tiers
| Tier     | Default Slots |
|----------|--------------|
| Strain   | 3            |
| Serious  | 2            |
| Critical | 1            |
| Lethal   | 1            |
| Dead     | toggle       |

---

## Setup & Hosting

This extension must be served over HTTPS. The easiest options:

### Option A — Netlify Drop (free, no account needed)
1. Go to https://app.netlify.com/drop
2. Drag the entire `injury-tracker/` folder onto the page.
3. Copy the URL Netlify gives you (e.g. `https://random-name.netlify.app`).

### Option B — GitHub Pages
1. Push this folder to a GitHub repo.
2. Enable GitHub Pages (Settings → Pages → Deploy from branch → `main / root`).
3. Your URL will be `https://<you>.github.io/<repo>/`.

### Option C — Local dev with `npx serve`
```bash
cd injury-tracker
npx serve . -l 3000
# Then use an ngrok tunnel for HTTPS: npx ngrok http 3000
```

---

## Loading into Owlbear Rodeo
1. Open any room in Owlbear Rodeo.
2. Click the puzzle-piece **Extensions** icon (top left).
3. Paste your manifest URL: `https://your-host.com/manifest.json`
4. Click **Add**.

---

## Using the Extension
- **Right-click any character token** → choose **Injuries**.
- Click any slot to open the edit modal.
- Type a description, add complications (Enter/comma to confirm, or click quick chips).
- Check **Treated** when the injury has been addressed.
- Click **Save** (or press Enter) — changes sync to all connected players instantly.
- Toggle **☠ Dead** at the bottom to mark a token as dead.

---

## Data Storage
Injury data is saved in each token's `metadata` under the key `com.injury-tracker/injuries`.
It persists with the scene and syncs automatically across all players.

## Files
```
injury-tracker/
├── manifest.json      ← Extension manifest (entry point)
├── background.html    ← Registers context menu on load
├── action.html        ← Info popover (top-left extension button)
├── popover.html       ← Main injury tracker UI
├── icon.svg           ← Extension icon
└── README.md
```
