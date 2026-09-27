# Everyday — studio site

Static marketing + legal site for the **Everyday** studio (small everyday-utility iPhone apps).

- **Source of truth:** this folder (`Everyday Site/docs/`) in the monorepo.
- **Deploy:** mirrored to a separate GitHub Pages repo via `../publish-everyday-site.sh`.
- **Live URL (once Pages is on):** https://hinkson.github.io/everyday-apps/

## Pages
- `index.html` — studio landing (all apps)
- `fonix.html` / `fonix-privacy.html` / `fonix-support.html` — Fonix
- `dues.html` / `dues-privacy.html` / `dues-support.html` — Dues
- `nudge.html` / `nudge-privacy.html` / `nudge-support.html` — Nudge (not on the
  App Store yet; the pages exist because ASC requires the support and privacy
  URLs at submission, and they must be three different pages)
- `heartprint.html` / `heartprint-privacy.html` / `heartprint-support.html`: Heartprint
  (pre-TestFlight, "Coming soon" like Nudge)
- `heartprint-match.html`: **where every Heartprint share link and QR code lands**
  (`#<code>`). It decodes the link in the browser and never sends it anywhere. Its
  type names and lines mirror `Heartprint/Engine/Archetype.swift`, and
  `ContentTests.matchPageMirrorsTheTypes` fails if the two drift. Renaming or moving
  this page breaks every link already sent.
- `privacy.html` / `support.html` — studio-level hubs
- `styles.css` — self-contained styles (no external deps)

## Before publishing (one-time)
1. Support contact is **support.altaaffirmations@gmail.com** (the existing shared inbox,
   reused across studios). To change it, swap the address across the HTML files.
2. Create the **everyday-apps** repo on GitHub (like altas-affirmations / howtomovie-apps),
   clone it to `~/Documents/GitHub/everyday-apps` (GitHub Desktop or terminal), then enable
   **Settings → Pages → deploy from `main` / root**. HTTPS remote:
   `https://github.com/hinkson/everyday-apps.git`.
3. Fonix and Dues are live and carry real App Store links. **Nudge does not.** When
   it ships, follow `Storefront/PLAYBOOK.md` §8: swap the `chip--soon` status in
   `nudge.html` for a real button, give the three `nudge*.html` entries in
   `Storefront/scripts/add_smart_app_banners.py` the app id, publish, then verify
   the **live** URL rather than the push.

Then: `./publish-everyday-site.sh "message"` (run `--check` first for a dry run).
