# VYBELIVE — company site

Static marketing site for **Vybelive LLC**, the software studio behind
KeyAudit Pro, TruckTap, and Sentry Access Control.

Live: https://livnlgnd.github.io/vybelive-site/

## Structure

```text
index.html          All page content
styles.css          Design system + responsive layout
main.js             Nav, scroll reveals, contact form
assets/             Logos, product screenshots, OG image, favicon
fonts/              Self-hosted Inter + Space Grotesk (no external requests)
.nojekyll           Tells GitHub Pages to serve files as-is
```

No build step. Open `index.html` directly or serve the folder:

```powershell
python -m http.server 8099
```

## Before publishing / updating

1. **Contact email** — replace `hello@vybelive.com` in `index.html`
   (contact section, footer, JSON-LD) and in `main.js` (`CONTACT_EMAIL`).
2. **Canonical / Open Graph URLs** — currently point at
   `https://livnlgnd.github.io/vybelive-site/`. Update them if the site moves
   to a custom domain, and add a `CNAME` file with that domain.
3. **Product links** — KeyAudit Pro, TruckTap, and Sentry Access all link to
   their live product sites. Update in `index.html` if they change.

## Deploy

GitHub Pages serves the `main` branch root.

```powershell
git add .
git commit -m "Update VYBELIVE site"
git push
```

Pages rebuilds automatically in about a minute.

## Editing design tokens

Colors, fonts, spacing, and radii live at the top of `styles.css` in `:root`.
The product visuals are plain screenshots in `assets/`; swap the files (keep
the aspect ratios roughly 16:9) to refresh them.
