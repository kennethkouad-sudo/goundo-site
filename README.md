# goundosakho.fr

One-page static site for Goundo Sakho, sage-femme libérale (Paris 15e). Plain HTML, CSS and JS; no build step.

- **Preview locally:** run `python3 -m http.server -d site` in this folder, then open http://localhost:8000.
- **Deploy:** Netlify publishes the `site/` folder only (see `netlify.toml`). Merging a pull request into `main` updates the live site.
- **Site files (all in `site/`):** `index.html`, `mentions-legales.html`, `img/`, `fonts/`, favicons, `robots.txt`, `sitemap.xml`.
- **Not part of the site (never published):** everything outside `site/`: `brand/` (unused colour variants and font files), `docs/`, `AUDIT.md`, `TODO-LEGAL.md`, `CLAUDE.md`.
- **Rules:** read `docs/BRIEF-site-goundo.md` (brand, content, decisions) and `CLAUDE.md` (build rules) before changing anything.
- **Doctolib (live since 5 Nov 2026):** to change the link, update `BOOKING_URL` in the script of `site/index.html` and the `href` of every link with the class `js-book` (header and hero in `index.html`, contact button, header in `mentions-legales.html`).
- **Before each deploy:** search `site/` for `À COMPLÉTER`; publish only when nothing is left.
