# Nazal Portfolio — Local Run & Git Ignore

Quick notes to get the project working locally and to keep large assets out of GitHub.

## What I changed
- Removed `import './style.css'` from `main.js` so the site works when you open `index.html` directly in a browser.
- Switched absolute paths to relative paths in `index.html` (`/style.css` → `style.css`, `/main.js` → `main.js`, `/assets/...` → `public/assets/...`).
- Added `.gitignore` to ignore `node_modules/` and `public/assets/` so the 100+ files won't be uploaded to GitHub.

## Run locally
- Option A — Quick (no server):
  1. Open `index.html` in your browser (double-click) — it should render fine now.

- Option B — Recommended (dev server with Vite):
  1. Run `npm install`
  2. Run `npm run dev`
  3. Open the URL shown by Vite (usually `http://localhost:5173`)

## If `public/assets` is already committed to GitHub
1. Add `public/assets/` to `.gitignore` (done).
2. Remove from the repo history with:

```bash
git rm -r --cached public/assets
git commit -m "Remove public/assets from repo and add to .gitignore"
git push
```

If you need to rewrite history (for sensitive or huge files), use `git filter-repo` or `BFG Repo-Cleaner` (careful — it's destructive).

## Need anything else?
If you want, I can:
- Install dependencies (`npm install`) and start the dev server for you.
- Move the assets to a different folder or set up Git LFS if you need them tracked but stored outside GitHub.
