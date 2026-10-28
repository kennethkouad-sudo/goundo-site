# CLAUDE.md: Goundo Sakho website

Instructions for Claude Code. Read this whole file, then `docs/BRIEF-site-goundo.md`, then `index.html`, before doing anything.

The work happens in two parts:

1. **Phase 0, coherence audit.** You check that this file, the brief and the code agree with each other. You write the result to `AUDIT.md`, then you **stop** and wait for the owner's approval. No file other than `AUDIT.md` changes during Phase 0.
2. **Phases 1 to 7, the build.** These start only after the owner has answered the audit, and they take those answers into account.

---

## 1. The project in brief

- One-page website in **French** for Goundo Sakho, *sage-femme libérale* (independent midwife) in Paris 15e, in practice since July 2026.
- Its single job is to turn a visitor into a patient who books an appointment.
- The design is finished and approved by Goundo (last approved version: 28 October 2026). **This is a production pass, not a redesign.** Do not change the layout, colors, type, copy or motion unless this file or the owner asks.
- Plain static site: HTML, CSS and a little vanilla JS. No framework, no bundler, no build step for the site itself. CSS and JS stay inline in `index.html`, as in the brief, section 9.

### Order of authority

When two sources disagree, follow the first one in this list, and record the disagreement in `AUDIT.md`:

1. What the owner tells you in this session.
2. `docs/BRIEF-site-goundo.md`: brand rules (section 3), hard constraints (section 7).
3. This file.
4. `index.html` as delivered.

**Never resolve a disagreement silently.** If the code and the brief disagree, the audit reports it, and the owner decides.

### Who the owner is

The person working with you is Goundo's partner, who manages the site for her. Anything about her health practice (services, fees, reimbursement, home visits, RPPS number, opening hours) must come from Goundo through the owner. **Never invent or guess these facts.** Use a visible placeholder such as `[À COMPLÉTER : numéro RPPS]` and list it as an open question.

---

## 2. Starting files

```
index.html                  the approved site (approved version of 28 October 2026)
img/                        logo, portrait, handwriting cut-outs (several colors each)
fonts/                      gloock-latin-400, instrument-sans-latin-400, instrument-sans-latin-600 (.woff2)
docs/BRIEF-site-goundo.md   the project brief (move it here from the root if it is not there yet)
CLAUDE.md                   this file
```

About `index.html`: it was written for a preview service that adds the document skeleton itself. So the file has **no** `<!doctype html>`, `<html>`, `<head>` or `<body>` tags, and it contains a meta tag that only that preview service uses: `<meta name="claude:viewport-fit-sides">`. Phase 2 turns it into a complete, standalone document.

---

## 3. Phase 0: coherence audit (do this first, then stop)

### 3.1 What you do

1. Read this file, the brief and `index.html` in full. Also look at every image in `img/`.
2. Check each item in the list in 3.3 against the actual files. **Verify; do not trust the list.** Some items may already be fixed, and some may be wrong.
3. Add anything else you notice: contradictions between this file and the brief, steps that cannot be carried out as written, missing information, risks for accessibility, performance or the law.
4. Write `AUDIT.md` in the format below.
5. Stop. Give the owner a short summary: how many findings, the blocking ones, and the questions waiting for them. Do not start Phase 1 until they reply.

### 3.2 Format of `AUDIT.md`

```markdown
# Audit, <date>

## Summary
<3 to 5 lines: is the plan coherent, what blocks the build, what needs the owner>

## Findings
| # | Where (file, section or line) | Finding | Type | Proposed fix | Owner decision needed? |
|---|---|---|---|---|---|

Type is one of: Contradiction, Gap, Rule breach, Risk, Fine as is.

## Questions for the owner
<numbered, one question each, answerable in a sentence>

## Build plan after the audit
<the phases below, adjusted to the findings, with anything you would add, drop or reorder>
```

### 3.3 Points to verify

Each one was spotted while preparing this file. Confirm it, correct it or dismiss it.

**Brand and handwriting rules (brief, section 3)**

1. *One handwritten phrase per section.* The hero holds two: "Bienvenue" and the "À chaque étape" note on the portrait. "Mes soins" also holds two: "Prends soin de ta santé" and "Je viens à vous". Yet the brief's own page structure (section 4) describes these exact placements. Ask the owner whether the rule means one per section or one per block. Do not remove anything yourself.
2. *Tilt of −2 to −3°.* The "Bienvenue" image in the hero and the "À très vite" signature in Parcours have no rotation. The pinned note, the "Pour qui" phrase and the service phrases do. Propose the fix, then wait for the owner.
3. *Mauve is never used for text.* The « » quote marks around the thesis title (`.memoire blockquote::before` and `::after`) are colored mauve. They are glyphs, so this is a text use. Propose mûre, or olive.
4. *Logo never under about 120px wide.* The footer logo is `7rem` (112px). On phones the header logo is `7.5rem` (120px), right at the limit.
5. *Token names.* The brief uses French token names (mauve-poudre, papier, encre…). The CSS uses English ones (`--blush`, `--paper`, `--ink`…). Check that every hex value matches the brief's table. Recommend whether to rename the CSS variables to the brief's names. Renaming is optional; the values must match.
6. *Label size.* The brief says labels are 12.5px. The CSS uses `.78rem`, which is 12.48px. This is fine; just confirm it.

**Content and copy**

7. *Placeholder email.* `contact@exemple.fr` appears in the JS constant `EMAIL` and in the visible text. Replacing it with **pro.goundo@gmail.com** is already decided (brief, section 6).
8. *Two names for one service.* The service title says "Préparation à l'accouchement". The meta description and the brief's open items say "préparation à la naissance". Ask which one Goundo wants. The two terms are used interchangeably in France.
9. *"15e" is written two ways.* The H1 uses a superscript `<sup>e</sup>`; every other mention is a plain "15e". Propose one style for the whole page.
10. *"Je viens à vous"* next to post-partum implies home visits. This is still unconfirmed (brief, section 8). It stays as it is unless the owner says otherwise. List it as a question.

**Technical**

11. *Fonts.* `fonts/` holds Instrument Sans 400 and 600 only. The CSS uses **500** in several places (navigation, hero facts, copy button), and the Google Fonts link also asks for italic 400. Check whether any italic is used at all. Propose either the variable version of Instrument Sans (a single file covering 400 to 700, for example from the npm package `@fontsource-variable/instrument-sans`, license SIL OFL) or dropping 500 in favor of 400 or 600. Do not change the look without the owner's approval.
12. *Booking buttons without JavaScript.* The `.js-mail` buttons point to `#rendez-vous` until the script turns them into `mailto:` links. In production, write the real `mailto:` link in the HTML, so the buttons also work without JS.
13. *Preview-only leftovers.* Remove the `claude:viewport-fit-sides` meta tag. Move the inline `style=""` attributes (on `<figure class="portrait">` and `<sup>`) into the stylesheet.
14. *Unused images.* Only 9 of the 35 files in `img/` are used. Propose whether to move the unused color variants to a `brand/` folder outside the deployed site. They must be kept; do not delete them.
15. *Image sizes.* The handwriting PNGs are large for the size they are displayed at (for example, `prenez-soin-vous` is 1400px wide). The portrait is an 800×800 JPEG shown cropped to 4:5.

**Legal and content gaps (brief, sections 7 and 8)**

16. *Mentions légales.* The page has none yet, and they are required. Check the brief: "single page" (section 7) against "mentions légales page or section" (section 8). Propose a separate `mentions-legales.html` linked from the footer, and ask the owner to confirm this exception to the single-page rule.
17. *Phone number.* The site does not show it yet. French law (LCEN, article 6) generally requires a phone number in the mentions légales of a professional website. Flag this so the owner can check it and confirm with Goundo. It does not mean the number has to appear in the main page.
18. *Hosting provider.* It has not been chosen, but the mentions légales must name it (name, address, phone). This decision is needed before Phase 4 can be finished.

### 3.4 What you must not do during the audit

- Do not edit `index.html`, the images or the brief.
- Do not install anything except to *read* package metadata, for example to check a font's license.
- Do not settle any open question yourself. Write it as a question.

---

## 4. Phase 1: set up the repository

Target structure (adjust it to the owner's answers to the audit):

```
/
├── index.html
├── mentions-legales.html      (Phase 4, if approved)
├── img/                       only the images the site uses (+ .webp versions)
├── fonts/                     only the font files the site uses
├── favicon.svg, favicon.ico, apple-touch-icon.png
├── og-image.jpg               1200×630
├── robots.txt, sitemap.xml
├── brand/                     unused color variants of the logo and handwriting (not linked from the site)
├── docs/BRIEF-site-goundo.md
├── AUDIT.md
├── CLAUDE.md
└── README.md                  how to preview locally and how to deploy, in 10 lines
```

- Run `git init`. First commit: the files exactly as delivered, so every later change can be reviewed as a diff.
- Make one commit per phase, with a clear message.
- Add a `.gitignore` for OS clutter and `node_modules/`, in case you use tooling such as image conversion or HTML validation. **Tooling never becomes part of the site.**
- Local preview: `python3 -m http.server`. Nothing else is needed.

## 5. Phase 2: turn `index.html` into a complete document

- Wrap the page in `<!doctype html>`, `<html lang="fr">`, `<head>`, `<body>`.
- Add `<meta charset="utf-8">` and `<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">`. The CSS already uses `env(safe-area-inset-*)`.
- Keep the existing `<title>` and meta description. Fix the meta description wording if the owner settles finding 8.
- **Self-host the fonts.** Replace the Google Fonts `<link>` tags with `@font-face` rules that point to `fonts/`, with `font-display: swap`. Preload the Gloock file and the regular Instrument Sans file. Keep the fallback stacks that are already in the CSS.
- Apply the findings the owner approved in Phase 0, and only those.
- Do not touch the CSS or JS beyond these points. In particular, leave the animations alone.

## 6. Phase 3: content that is already decided

- Email: **pro.goundo@gmail.com**, in the JS constant, in the visible text and in the hardcoded `mailto:` links. The subject stays "Prise de rendez-vous".
- LinkedIn: already correct. It is the only social link she wants.
- **Do not add** any of these until the owner gives them: phone number on the main page, practice address, Doctolib link, opening hours, nearest metro, *conventionnée* status, prices, reimbursement wording, details of the birth-preparation programme, the thesis PDF or its HAL-Dumas link.
- When Doctolib arrives later, every "Prendre rendez-vous" / "Demander un rendez-vous" button switches to it. Make this a one-line change: keep the booking URL in one place in the JS, next to `EMAIL`, and also hardcode it in the HTML.

## 7. Phase 4: mentions légales

If the owner approves a separate page (finding 16): create `mentions-legales.html` with the same header, footer, fonts and colors as the home page, and a simple text layout. Add a "Mentions légales" link in the footer of both pages.

Contents (in French). Use placeholders for anything you have not been given:

- Éditrice du site : Goundo Sakho, sage-femme libérale.
- Adresse professionnelle : [À COMPLÉTER].
- Contact : pro.goundo@gmail.com, téléphone [À COMPLÉTER, voir point 17 de l'audit].
- Inscription à l'Ordre des sages-femmes : conseil départemental de [À COMPLÉTER], numéro RPPS [À COMPLÉTER].
- Directrice de la publication : Goundo Sakho.
- Hébergeur : [À COMPLÉTER : raison sociale, adresse, téléphone].
- Données personnelles : the site sets no cookies, has no analytics and no form. E-mails sent to the address are used only to answer the request. If analytics or a form are ever added, this section must be rewritten first.
- Crédits : design and photo credits, if the owner wants them.

**Do not publish legal wording you are unsure of as fact.** List the open points at the top of `AUDIT.md` (or in a short `TODO-LEGAL.md`), so the owner can have them checked.

## 8. Phase 5: images and performance

- Make a `.webp` version of each image the site uses. Use lossless WebP (or quality 90 or higher) for the handwriting and the logo: they have transparency and thin strokes that must stay crisp. Size each one at about 2× its largest displayed width.
- Serve them with `<picture>`: `.webp` first, the original as fallback. Keep the `alt` texts **exactly** as they are.
- Add `width` and `height` attributes to every `<img>` to avoid layout shift.
- Add `loading="lazy"` and `decoding="async"` to images below the fold. **Do not** add them to the hero images: logo, "Bienvenue", portrait, "À chaque étape".
- Portrait: one 4:5 crop at about 900×1125, and one smaller one for phones (`srcset`). Keep the framing that `object-position: 48% 30%` gives today.
- Target: the whole page under 600 KB on first load, fonts included.

## 9. Phase 6: favicon, sharing and search

- **Favicon.** Propose two options to the owner before you make the files:
  - a "G" in Gloock, nacre on a mûre circle;
  - the logo's droplet in olive on mauve poudré.

  The thin line of the full logo does not survive at 16px, so do not use it. Deliver `favicon.svg`, `favicon.ico` (32px) and `apple-touch-icon.png` (180px).
- **Sharing image (`og-image.jpg`, 1200×630).** The portrait on a mauve-poudré background, the logo in mûre, and the line "Sage-femme libérale à Paris 15e". Add the `og:` and `twitter:card` tags. Show the image to the owner before committing it.
- `robots.txt` and `sitemap.xml`, with the final domain. Use a placeholder until the domain is known.
- Structured data (JSON-LD): add it only after the address is confirmed, and only with facts given by the owner.
- **No hidden keywords, no keyword stuffing** (brief, section 7). Visibility comes from real content and honest `alt` texts.

## 10. Phase 7: deployment

- Use the host the owner chose during the audit. The site has no build, so deployment means publishing the repository root (or a `public/` folder, if you created one).
- Connect the domain, and check that HTTPS and the redirect from `www` to the bare domain (or the other way round) work.
- Put the final hosting details into the mentions légales.

---

## 11. Acceptance checks (run before saying a phase is done)

- [ ] No horizontal scrolling at 360px, 390px, 768px, 1280px or 1440px wide.
- [ ] No errors in the browser console. The HTML passes validation (for example `npx html-validate index.html`).
- [ ] Chrome: scroll-driven animations play. Firefox: the page is static and complete, and the icons still draw themselves.
- [ ] With `prefers-reduced-motion: reduce`: nothing moves and everything is visible.
- [ ] With JavaScript disabled: all content is visible, the email address is readable, and the booking buttons open an e-mail.
- [ ] Lighthouse (phone): Accessibility ≥ 95, Best Practices ≥ 95, SEO ≥ 95, Performance ≥ 90.
- [ ] Every handwritten image has an `alt` text that matches its phrase. Every icon is `aria-hidden`.
- [ ] Contrast: body text and labels pass WCAG AA on their background. Mauve is not used for any text.
- [ ] No request to `fonts.googleapis.com` or any other outside domain, except the LinkedIn link.
- [ ] Brand check against the brief (section 3): same hex values, Gloock never bold or italic, handwriting used as images only.
- [ ] Hard constraints (brief, section 7): no testimonials, no reviews, no invented fees or services, French only.

Before you deploy, compare screenshots of the final page at 390px and 1280px with the approved preview. They should look the same, apart from approved fixes.

## 12. Standing rules (for every session)

- The site stays **in French**. Code comments and commit messages can be in English.
- Use *vous* everywhere. *Tu* appears only in her handwritten notes.
- **Never change the copy without the owner's approval.** If something reads wrong, suggest a change; do not make it.
- Her handwriting stays as images. It never becomes a font, an SVG trace or text. Follow all five handwriting rules in the brief.
- Line icons: 48×48 grid, stroke 1.4, mûre line, one olive detail, in a round badge. A new icon must match this set.
- No frameworks, no CSS libraries, no tracking, no cookies, no third-party embeds.
- When the owner asks for a change that breaks a rule in the brief, say which rule it breaks before doing anything.
- Keep `docs/BRIEF-site-goundo.md` current. When the owner approves a change to the design or content, record it in the brief, in the same commit.
