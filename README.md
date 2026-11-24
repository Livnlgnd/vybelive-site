# VYBELIVE — company site

Static marketing site for **Vybelive LLC**, the software studio behind
KeyAudit Pro, TruckTap, and Sentry Access Control.

Live: https://livnlgnd.github.io/vybelive-site/

## Pages

| File | Purpose |
| --- | --- |
| `index.html` | Landing page: positioning, product overview, contract work, contact |
| `products.html` | Product index |
| `keyaudit-pro.html` | KeyAudit Pro detail page |
| `trucktap.html` | TruckTap detail page |
| `sentry-access.html` | Sentry Access Control detail page |
| `services.html` | Contract services and process (`services.html#process`) |
| `about.html` | Studio story and values |
| `contact.html` | Project brief form |
| `404.html` | Branded not-found page |

## Structure

```text
*.html              Pages listed above
styles.css          Design system, components, subpage layouts, responsive rules
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

1. **Contact email** — replace `hello@vybelive.com` in every page (header/footer)
   and in `main.js` (`CONTACT_EMAIL`).
2. **Canonical / Open Graph URLs** — currently point at
   `https://livnlgnd.github.io/vybelive-site/`. Update them if the site moves
   to a custom domain, and add a `CNAME` file with that domain.
3. **Product links** — each product page links to its live product site.
   Update in the relevant HTML file if they change.
4. **Sitemap** — `sitemap.xml` lists every page. Keep it in sync when adding one.

## Deploy

GitHub Pages serves the `main` branch root.

```powershell
git add .
git commit -m "Update VYBELIVE site"
git push
```

Pages rebuilds automatically in about a minute.

## Editing design tokens

The site uses a light theme. Colors, fonts, spacing, and radii live at the top
of `styles.css` in `:root`. Product visuals are screenshots in `assets/`; swap
the files (keep roughly 16:9) to refresh them.
