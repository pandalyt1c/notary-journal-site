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
- `states.html` — "Notary Journal Requirements by State" (50 states + DC table; the SEO hub)
- `california.html` — "California Notary Journal Requirements" (flagship deep-dive)
- `privacy.html`, `terms.html`, `support.html` — legal/support
- `style.css` — shared brand styling (notarial purple)
- `icon.png` — the app icon (1024)

## Web companion (SEO pages)
`states.html` + `california.html` are the free, indexable "dual-surface" pages. They target notary-journal search intent ("does [state] require a notary journal", "notary journal template/app") and funnel to the App Store.
- Source data: per-state journal mandates verified against each state's statute / SOS handbook as of 2026-07-01. Every mandatory-state claim is cited in the table's "Basis" column.
- Accuracy: laws change; each page carries a "not legal advice, verify with your commissioning authority" disclaimer. Re-verify recently-changed states before major edits: MO (2020), KS (2022), NY/IL/DE (2023), OK (2025), UT (from 2026-05-06).
- The App Store CTA links to `https://apps.apple.com/app/id6786334880`. That link is live only after Apple approves the app (in review as of 2026-07-01); it will 404 until then.
- To add more state deep-dives later, copy `california.html` and swap the state-specific statute content (data is in `app-studio/app3-notary-journal/` research notes).
