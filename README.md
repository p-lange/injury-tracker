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
