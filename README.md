# goundosakho.fr

One-page static site for Goundo Sakho, sage-femme libérale (Paris 15e). Plain HTML, CSS and JS; no build step.

- **Preview locally:** run `python3 -m http.server` in this folder, then open http://localhost:8000.
- **Deploy:** Netlify publishes this repository. Merging a pull request into `main` updates the live site.
- **Site files:** `index.html`, `mentions-legales.html`, `img/`, `fonts/`, favicons, `robots.txt`, `sitemap.xml`.
- **Not part of the site:** `brand/` (unused colour variants of the logo and handwriting), `docs/`, `AUDIT.md`, `TODO-LEGAL.md`, `CLAUDE.md`.
- **Rules:** read `docs/BRIEF-site-goundo.md` (brand, content, decisions) and `CLAUDE.md` (build rules) before changing anything.
- **Before each deploy:** search for `À COMPLÉTER`; publish only when nothing is left.
