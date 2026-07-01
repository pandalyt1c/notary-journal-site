# Notary Journal — static site (GitHub Pages ready)

Plain HTML + one CSS file. No build step. Landing page plus the three pages Apple needs.

## Before you publish (fill 5 placeholders)
Find/replace across the `.html` files:
- `[SUPPORT_EMAIL]` → a public support email (5 spots: privacy 1, terms 2, support 2). Avoid the personal gmail; a forwarding alias is better.
- `[STATE/JURISDICTION]` → your governing-law state (terms.html, 1 spot).

Quick check after: `grep -rc "\[SUPPORT_EMAIL\]\|\[STATE/JURISDICTION\]" *.html` should print 0 for every file.

## Host on GitHub Pages
1. New GitHub repo (e.g. `notary-journal-site`), public.
2. Copy the contents of this `site/` folder to the repo root and push to `main`.
3. Repo → Settings → Pages → Source = "Deploy from a branch", Branch = `main`, folder `/ (root)` → Save.
4. After a minute the site is live at `https://<user>.github.io/notary-journal-site/`.

## The two URLs App Store Connect requires
- **Privacy Policy URL:** `https://<user>.github.io/notary-journal-site/privacy.html`
- **Support URL:** `https://<user>.github.io/notary-journal-site/support.html`

(A custom domain works too — set it under Pages → Custom domain.)

## Files
- `index.html` — landing
- `privacy.html`, `terms.html`, `support.html` — legal/support
- `style.css` — shared brand styling (notarial purple)
- `icon.png` — the app icon (1024)
