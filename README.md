# Pirate Chest

Open Pirate Chests in your browser: any amount, from 1 to a quadrillion at once.

**Play:** https://timmeyfn.github.io/FortniteTokenPractise/

## Features
- Full animated chest opening for up to 100 chests. Bigger batches use a fast view, and anything over 2 million is counted instantly with exact odds maths.
- ∞ Auto-open mode.
- Pirate Token cinematic: zoom in, rumble, gold rings, then the Pirate Shop Access animation.
- Inventory and odds, plus a 🍀 luck meter for each batch.
- Live anonymous leaderboard and recent big pulls, with no setup needed.
- An update log that pops up automatically when there's a new version.

## How the leaderboard works
Scores are posted to a public channel on [ntfy.sh](https://ntfy.sh), and each browser keeps its own copy of the board. Visitors re-post a snapshot every few hours, so the board survives past ntfy's 12-hour message limit. It's anonymous and has no accounts, so it isn't cheat-proof.

## Adding an update
Edit `APP_VERSION` and add an entry at the top of `UPDATES` in `index.html`. Everyone sees the update log automatically the next time they visit.
