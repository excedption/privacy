# Excedption Games — Privacy Policy Site

Single Privacy Policy that covers all games published by Excedption. Designed to be deployed free of charge on GitHub Pages and to require only a one-line edit when a new game is released.

## Files

| File | Purpose |
|---|---|
| `index.html` | The policy text. Dynamic fields are filled in from `games.json`. |
| `games.json` | Single source of truth: publisher info, dates, and the list of covered games. |
| `style.css` | Mobile-friendly styling. |
| `README.md` | This file (not published). |

## Deploying to GitHub Pages (one-time)

1. Create a new **public** GitHub repository, e.g. `game-policies`.
2. Copy the four files above into the repo root (or a `docs/` folder — see step 4).
3. Commit and push.
4. Go to **Settings → Pages** in the repo and configure:
   - **Source**: Deploy from a branch
   - **Branch**: `main` — `/ (root)` (or `/docs` if you chose that folder)
5. After a minute, your URL will be live at:
   ```
   https://<your-username>.github.io/game-policies/
   ```
6. Paste this URL into both stores:
   - **Google Play Console** → App content → Privacy Policy URL
   - **App Store Connect** → App Privacy → Privacy Policy URL

Every game in the publisher's portfolio uses the same URL.

## Adding a New Game (2 steps)

When a new game is released:

1. Open `games.json` and append an object to the `games` array:
   ```json
   {
     "slug": "my-new-game",
     "name": "My New Game",
     "tagline": "Short genre tag"
   }
   ```
2. Bump `lastUpdated` to today's date.

Commit and push. The policy page updates automatically — no HTML editing needed.

The list of games is **informational**, not legally binding. The policy applies to every game released by the same publisher regardless of whether the list has been updated, per the last paragraph of section 1. However, keeping the list current is good practice for store reviewers and users.

## Changing Contact Info

Edit `contactEmail` and `publisher` in `games.json`. Every reference updates automatically.

## Making Substantive Policy Changes

If the underlying data practices change (e.g. adding a new third-party SDK, starting to collect new data), you must update `index.html` itself and bump both `lastUpdated` and `effectiveDate` in `games.json`. For material changes, show an in-app notice before the effective date per section 12 of the policy.

## Local Preview

Open `index.html` directly in a browser, or run a simple server:

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Legal Note

This template was drafted to cover the current Excedption Games stack: **Capacitor wrapper + Unity Ads + in-app purchase for ad removal, no servers, no accounts**. If the stack changes (e.g., cloud saves, analytics SDK, user-generated content, chat, leaderboards requiring login), the policy needs a human review — ideally by a lawyer.

The template is not legal advice.
