# Everyday — studio site

Static marketing + legal site for the **Everyday** studio (small everyday-utility iPhone apps).

- **Source of truth:** this folder (`Everyday Site/docs/`) in the monorepo.
- **Deploy:** mirrored to a separate GitHub Pages repo via `../publish-everyday-site.sh`.
- **Live URL (once Pages is on):** https://hinkson.github.io/everyday-apps/

## Pages
- `index.html` — studio landing (all apps)
- `fonix.html` / `fonix-privacy.html` / `fonix-support.html` — Fonix
- `dues.html` / `dues-privacy.html` / `dues-support.html` — Dues
- `privacy.html` / `support.html` — studio-level hubs
- `styles.css` — self-contained styles (no external deps)

## Before publishing (one-time)
1. Support contact is **support.altaaffirmations@gmail.com** (the existing shared inbox,
   reused across studios). To change it, swap the address across the HTML files.
2. Create the **everyday-apps** repo on GitHub (like altas-affirmations / howtomovie-apps),
   clone it to `~/Documents/GitHub/everyday-apps` (GitHub Desktop or terminal), then enable
   **Settings → Pages → deploy from `main` / root**. HTTPS remote:
   `https://github.com/hinkson/everyday-apps.git`.
3. Fill in the real **App Store links** (the `href="#"` "Download on the App Store"
   buttons in `fonix.html` and `dues.html`) once each app is live.

Then: `./publish-everyday-site.sh "message"` (run `--check` first for a dry run).
