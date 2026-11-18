# Pirate Chest — GitHub Pages

## 1. Put it on GitHub Pages
1. Unzip this file. You'll get a folder containing `index.html`, an `img` folder, this README and `firebase-rules.json`.
2. Sign in at github.com and click **New repository**. Name it `pirate-chest`, make it **Public**, and click **Create repository**.
3. On the next page, click **uploading an existing file**.
4. Open the unzipped folder on your computer and select **`index.html` and the `img` folder together** (Ctrl+A, or Cmd+A on a Mac).
5. **Drag them into the GitHub page** in your browser. Dragging keeps the `img` folder intact, but the "choose your files" button can't pick folders, so use drag-and-drop.
6. Wait until all 10 files are listed (index.html plus 9 files inside img/), then click **Commit changes**.
7. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, then **main** and **/ (root)**, and click **Save**.
8. Wait about a minute. Your site is at `https://YOUR-USERNAME.github.io/pirate-chest/`.

Drag the *contents* of the folder, not the folder itself. Otherwise the site ends up one level deeper, at `.../pirate-chest/pirate-chest/`.

## 2. Turn on the shared leaderboard (free Firebase)
GitHub Pages only hosts files, so the leaderboard needs somewhere to store scores.
1. Go to console.firebase.google.com, click **Create a project**, and name it `pirate-chest` (you can skip Analytics).
2. In the left menu, click **Build → Realtime Database → Create Database**, pick a location, and start in **locked mode**.
3. Open the **Rules** tab, replace everything with the contents of `firebase-rules.json`, and click **Publish**.
4. Copy the database URL shown on the **Data** tab. It looks like `https://pirate-chest-default-rtdb.firebaseio.com`.
5. In `index.html`, find `const FIREBASE_URL = '';` and paste the URL between the quotes. Commit the change on GitHub.

Until you do this, the site works fine but the leaderboard only shows your own score.

## Notes
- You can open any number of chests (up to 100 million at once). Up to 100 get the full animation. Bigger batches switch to a fast canvas view showing up to 20,000 chests, plus a results bar that totals every reward.
- Each visitor's anonymous ID, inventory and token count are saved in their own browser.
- Because a static site rolls chests in the browser, a determined person could fake a token. The database rules limit this: a player's total can only go up, by at most 5,000 tokens per update and at most once every 10 seconds, and names must look like "Anonymous #1234".
- The Pirate Token animation is `img/pirate-token.mp4`, with the green screen already removed. The top half holds the colour and the bottom half holds the see-through mask, and the page combines them as it plays.
