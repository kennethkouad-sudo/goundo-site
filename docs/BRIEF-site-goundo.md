# Goundo Sakho website: project brief

This brief carries over all the context from the conversation where the site was designed. It covers what exists, what was decided and why, and what is still open. Read it fully before changing anything.

## 1. Who and what

- **Client:** Goundo Sakho, *sage-femme libérale* (independent midwife), Paris 15e. She started her own practice in July 2026.
- **Deliverable:** a one-page landing site in **French** that turns a stranger into a patient: "j'aime ce que je vois, je prends rendez-vous".
- **Audience:** a young woman of 22 asking about contraception, a mother of 49, a woman in menopause, a couple trying for a baby, pregnant women, new mothers. The site has to speak to all of them.
- **Ambition:** a serious, professional midwife who also has a voice, like a content creator. The look should be calm but with character and real color, never all white or all beige. She called it "something a financier would find polished".

## 2. Where everything lives

- **Current site (published preview, approved version of 28 October 2026):** https://claude.ai/artifact/6suw9n3sm9A3uTFuutrY1v
- **Earlier preview (before the October tune-up, kept for reference):** https://claude.ai/artifact/GAy7QLewiSqkTK9c8nfR1Z
- **Brand guide (charte graphique):** https://claude.ai/artifact/P6WBNyJ3XEVuaQPWUCNEtn
- **Attached zip `site-goundo.zip`:**
  - `index.html`: the full site, one self-contained file (HTML, CSS and JS).
  - `img/`: logo, portrait, and handwriting cut-outs, each in several colors.
  - `fonts/`: Gloock and Instrument Sans as .woff2 files, for self-hosting later.
  - this brief.
  - `CLAUDE.md`: the build instructions for Claude Code, starting with a coherence audit.

## 3. Brand system (follow exactly)

### Colors

| Token | Hex | Use |
| --- | --- | --- |
| mauve-poudre | `#E9D6DC` | Signature light background (header, hero, parcours) |
| mauve | `#B07B8C` | Original logo color. Accents and photo backdrops only. **Never use it for text** (contrast too low). |
| mure | `#4A2A36` | Headings, dark bands (who, contact, footer) |
| olive | `#5F6640` | Action color: buttons, small-caps labels, one highlighted word |
| olive-texte | `#5A613D` | Olive for small text on mauve poudré only (labels, timeline years, service stage). `#5F6640` reaches only 4.37:1 there; this reaches 4.71:1 (WCAG AA). Added 28 October 2026 (audit, finding 19). |
| papier | `#F7F0F2` | Page background, used instead of white |
| encre | `#3A2430` | Body text |
| encre-douce | `#6E5762` | Secondary text |
| nacre | `#F7EEF1` | Text on mûre or olive |
| nacre-douce | `#D9C2CB` | Secondary text on mûre |

In the CSS the tokens keep their English names (`--blush`, `--paper`, `--ink`…), with a comment mapping each one to the names above. The values are what must match.

Proportions are roughly 60% light (mauve poudré or papier), 30% mûre and 10% olive. The site is deliberately light-theme only, a branded look rather than a dark-mode-aware one.

### Type

- **Gloock** for headings: one weight, never bold or italic.
- **Instrument Sans** for body text, weights 400 to 600, self-hosted as the variable font (one latin `.woff2` file covering 400–700, SIL OFL). No italic is used.
- Labels are small caps in olive, 12.5px, letter-spacing 0.14em, uppercase. On mauve poudré they use olive-texte; on mûre bands they use nacre-douce (olive is unreadable on mûre).
- If Gloock ever has to be replaced (Canva), use **DM Serif Display**.
- Ordinals such as "15e" use a raised "e" everywhere in visible text (the page title and meta description stay plain, since they cannot be formatted).
- The « » marks around the thesis title are olive (never mauve).

### Logo

The word "Goundo" in a thin line with droplet terminals. It comes in mûre, mauve poudré, olive and mauve, as transparent PNGs. The line is very thin, so never display it under about 120px wide. This includes the footer logo (120px) and the header logo on small phones (it must not shrink below 120px).

### Her handwriting: the signature of the brand

These are real phrases written by Goundo, cut out as transparent PNGs. The versions the site uses are in `img/`; the other colors (and the two newer phrases) are kept in `brand/`, which is not part of the site:

| File | Phrase | Where it is used |
| --- | --- | --- |
| `bienvenue-*` | Bienvenue | Hero, above the H1 (animates as if being written) |
| `chaque-etape-*` | À chaque étape | Note pinned to her portrait |
| `sans-tabou-*` | On en parle sans tabou | "Pour qui" band |
| `prends-soin-*` | Prends soin de ta santé | Gynecology service row |
| `je-viens-*` | Je viens à vous | Post-partum service row |
| `a-tres-vite-*` | À très vite | Signature at the end of her bio |

Two newer phrases are in the zip too: `prenez-soin-vous-*` ("Prenez soin de vous !", used on her business card) and `a-tres-vite2-*`. The second one was written without the accent on the A, so prefer the original `a-tres-vite-*` on the site.

Rules for the handwriting:

1. At most one handwritten phrase per block (a column, or a service row). A section may hold two, as the hero and "Mes soins" do. It is a margin note, never the headline. (Clarified by the owner, 28 October 2026.)
2. Always pair it with printed text that carries the actual information.
3. Use mûre or olive on light backgrounds and the mauve-poudré (`-blush`) version on dark ones.
4. Tilt it slightly (−2 to −3°). "Bienvenue" and "À très vite" are tilted −2.5° (28 October 2026).
5. Do not turn her handwriting into a font. Keep it as images.

### Line icons (approved 28 October 2026)

Hand-drawn line icons sit next to the hero facts and next to each service. They are drawn in the spirit of the logo: a thin line with a droplet end.

- Inline SVG, 48 × 48 grid, stroke 1.4, round caps and joins, no fill.
- Line in mûre, one detail in olive, and often one small filled olive dot (the droplet).
- Each sits in a round badge: papier on mauve-poudré backgrounds, mauve poudré on papier.
- Set: Eiffel Tower (Cabinet à Paris 15e), calendar with a tick (Consultations sur rendez-vous), graduation cap with tassel (Diplômée de l'Université Paris Cité), pregnant silhouette (Suivi de grossesse), breath curls (Préparation), tulip (Suivi gynécologique), crescent moon and star (Post-partum), lotus (Rééducation du périnée).
- Icons are decoration (`aria-hidden`); the printed text carries the information. They are not her handwriting and do not count toward the handwriting rules.

### Voice

- Use *vous* on the site. *Tu* appears only in her handwritten notes ("Prends soin de ta santé").
- Short, plain sentences, first person ("je"), no jargon.
- Avoid template phrases like "accompagnement bienveillant et personnalisé". Use real specifics instead.

## 4. Page structure (as built)

1. **Header** (mauve poudré): logo, nav (Soins, Parcours, Mémoire) and an olive "Prendre rendez-vous" button.
2. **Hero** (mauve poudré):
   - handwritten "Bienvenue";
   - H1 "Sage-femme libérale à Paris 15e, pour votre santé de *femme*, à tout âge.";
   - a lead paragraph and two buttons;
   - a 4:5 portrait on an offset mauve slab, with the "À chaque étape" note pinned like paper;
   - below both columns, a full-width row of three facts, each with its line icon before the text: Eiffel Tower + "Cabinet à Paris 15e", calendar + "Consultations sur rendez-vous", graduation cap + "Diplômée de l'Université Paris Cité".
3. **Le métier** (papier): what a *sage-femme libérale* actually does, plus four facts (Grossesse, Gynécologie, Prescriptions, Orientation).
4. **Pour qui** (mûre): "Vous pouvez venir me voir si…" with five situations, and the "On en parle sans tabou" handwriting.
5. **Mes soins** (papier): five services as editorial rows, not cards. Each title has its line icon in a round badge to its left.
   - Suivi de grossesse.
   - Préparation à la naissance (this term everywhere: title, meta description, brief; decided 28 October 2026).
   - Suivi gynécologique: highlighted row, with chips for Consultation IST, Infection vaginale, Infection urinaire, Renouvellement de contraception, Consultation pré-conceptionnelle, Check-up annuel.
   - Post-partum.
   - Rééducation du périnée.
6. **Parcours / Qui suis-je** (mauve poudré): a short bio, signed with "À très vite" and the logo, and the timeline split into two tracks, each from most recent to oldest, with full years everywhere:
   - **Expérience**
     - Depuis 2026: Installation en libéral, Paris 15e.
     - 2025 – 2026: Sage-femme référente du diagnostic préimplantatoire, PMA, Hôpital Antoine-Béclère, Clamart.
     - 2025: Sage-femme en soins à domicile, Fondation Santé Service, Levallois-Perret.
   - **Formation**
     - 2021 – 2026: Master en sciences maïeutiques, Université Paris Cité.
     - 2019 – 2021: Licence de médecine (PACES), Université Sorbonne Paris Nord, ranked 4th out of 206.
7. **Mémoire** (papier): the title of her thesis, shown as a large quote:
   - « Le groupe de parole dans la prise en charge des femmes concernées par les mutilations sexuelles féminines »;
   - Université Paris Cité, 2026, to be published on HAL-Dumas;
   - she wants it **mentioned openly**;
   - for now the button invites people to email her for the PDF.
8. **Rendez-vous / Contact** (mûre):
   - booking by email, with the subject line "Prise de rendez-vous";
   - the email shown as text with a copy button;
   - the practice address, shown under the e-mail subject line as « Cabinet : 62 rue des Entrepreneurs, 75015 Paris » (wording approved 28 October 2026), so it reads as her cabinet, not as the only place she works (she also works elsewhere);
   - a "Dans votre message" checklist (items: name; "Le type de consultation (grossesse, gynécologie, post-partum…)"; availability; a phone number to call back), followed by the plain line "Inutile de détailler votre situation par e-mail, on en parlera en consultation." It is styled as a page from her notebook taped onto the mûre band: papier card tilted 1.5°, a strip of mauve-poudré tape, a mauve margin rule, ruled lines and empty olive tick boxes;
   - an urgent-care line: "appelez le 15", inside the note on a mauve-poudré strip, with "15" in a mûre circle.
9. **Footer**: logo, name, LinkedIn (the only social link she wants) and a "Mentions légales" link.
10. **`mentions-legales.html`**: a separate page with the same header, footer, fonts and colors, linked from the footer of both pages. It is the one exception to the single-page rule. Sections (built 28 October 2026): Éditrice du site (name, cabinet address, e-mail, directrice de la publication; no phone number, as decided); Profession réglementée (title, Ordre council, RPPS, professional rules); Hébergeur (Netlify, Inc., 101 2nd Street, San Francisco, CA 94105, États-Unis; support@netlify.com, since Netlify publishes no phone number); Données personnelles (no cookies, analytics or form; use of e-mails; 3-month deletion; rights and CNIL). The owner approved the wording on 28 October 2026, including the code de déontologie range "articles R. 4127-301 à R. 4127-367". No credits section unless the owner asks for one. Missing facts are shown as visible `[À COMPLÉTER : …]` placeholders; see `TODO-LEGAL.md`.

## 5. Motion (already built; keep it restrained)

- **On load (hero):** "Bienvenue" writes itself in (clip-path wipe) while the H1, lead text, buttons and facts rise in sequence. The mauve slab slides up and the photo unveils from the bottom with a slow zoom-out. The "À chaque étape" note drops in, then floats very slightly.
- **On scroll:** this uses CSS scroll-driven animations (`animation-timeline: view()`), wrapped in `@supports`, so Firefox shows a static page. Labels, headings and paragraphs rise into place, list items are staggered, and every handwritten note "writes" itself in. The timeline line draws downward and its dots pop in.
- **Line icons:** each icon draws itself stroke by stroke (stroke-dashoffset), then its droplet dot pops in. The hero facts also write their text in from left to right. Triggered by an IntersectionObserver, so it also works in Firefox. On load the hero facts wait until "Bienvenue" has written itself; reached later by scrolling, they draw at once.
- **On hover:** button arrows nudge forward, service icon badges tilt slightly, service titles shift right, chips turn mûre, and nav links get an underline that draws in.
- Everything is turned off under `prefers-reduced-motion`.

## 6. Real contact details (from her business card)

- Email: **pro.goundo@gmail.com** (on the site since 28 October 2026: visible text, JS constant `EMAIL`, and `mailto:` links written in the HTML with the subject "Prise de rendez-vous").
- Phone: **07 66 96 67 81**. Decided 28 October 2026: shown on **neither** page. The LCEN may require a phone number in the mentions légales; this is tracked in `TODO-LEGAL.md`.
- Practice address: **62 rue des Entrepreneurs, 75015 Paris**. Decided 28 October 2026: shown in the contact section and in the mentions légales, as her cabinet (she also works in other places).
- LinkedIn: https://www.linkedin.com/in/goundo-sakho-4746551a8/
- Doctolib: not set up yet. When she has a link, the header "Prendre rendez-vous" and the hero "Demander un rendez-vous" switch to it; "Écrire un e-mail" stays an e-mail link. The link goes in `BOOKING_URL` in the script and in the `href` of every `js-book` link, on both pages (see `README.md`).
- Domain: **goundosakho.fr** (bought; DNS access comes later).
- Host: **Netlify**, publishing this GitHub repository.

## 7. Hard constraints (do not break)

- **No patient testimonials or Google reviews on the site.** The French code of ethics for midwives (*code de déontologie des sages-femmes*) forbids third-party testimonials in professional communication. A plain "Voir sur Google" link to her listing is the safe alternative.
- **No hidden keywords or paid placement.** She wondered about showing up for "sage-femme noire". The honest route is her photo front and center, accurate alt text, and real articles later, for example on care for Black women and representation in perinatal health.
- **Accuracy on health and fees.** Do not invent services, prices or reimbursement rules. A systematic €10 supplement (*dépassement d'honoraires*) on reimbursed sessions may not be allowed for a *conventionnée* midwife. She was told to check with her CPAM or the Ordre before publishing any fee.
- Keep the site in French, single page, and simple. The only exception is the separate mentions légales page (approved 28 October 2026).

## 8. Open items to settle in the tune-up

- [x] Replace the placeholder email with pro.goundo@gmail.com, and decide whether to show the phone number and address. *Decided 28 October 2026: email everywhere; address in the contact section and the mentions légales; phone on neither page.*
- [ ] Have Goundo review the copy I wrote in her voice, especially:
  - [ ] the bio sentence "on soigne mieux quand on prend le temps d'écouter";
  - [x] "Je viens à vous" next to post-partum, which implies home visits; confirm she does them. *Confirmed 28 October 2026: she does home visits; the phrase stays.*
- [ ] Mémoire: add the PDF or the HAL-Dumas link once it is published.
- [ ] Doctolib link, when available. *Which buttons switch is decided (section 6).*
- [ ] Practical info: opening hours, access (nearest metro), whether she is *conventionnée*, and a sentence on reimbursement once confirmed. *(Address decided, see section 6.)*
- [ ] Optional: a "Préparation à la naissance" detail. A branded PDF of her 7-session programme exists: anatomie, travail et accouchement, gestion de la douleur, allaitement, soins de puériculture, post-partum, and a 7th theme still to be confirmed.
- [x] Legally required **mentions légales** page or section: identity, RPPS number, address, hosting provider. Add a privacy note if any form or analytics is added. *Decided 28 October 2026: separate page `mentions-legales.html`, host Netlify. Still missing: RPPS number and Ordre council (placeholders), legal review (see `TODO-LEGAL.md`).*
- [ ] Favicon, social share image (OG), meta description check, image compression (WebP), and self-hosted fonts. *Meta description decided ("préparation à la naissance"); fonts: variable Instrument Sans. Work scheduled in the build phases.*
- [ ] Re-export "Prends soin de ta santé": the accent on "santé" is cut at the top of the image (confirmed 28 October 2026). The current image stays until then.
- [ ] A higher-resolution portrait, if one becomes available. Until then the site uses the best 4:5 crop of the current 800×800 photo (640×800).
- [x] Images (Phase 5, 28 October 2026): every image has a WebP version served through `<picture>`, with the original as fallback and unchanged alt texts. Handwriting: lossless WebP at full size (smaller and sharper than a resized copy). Logos: lossless WebP at 2× their displayed width. Portrait: 4:5 crop of the 800×800 photo matching the approved framing, 640×800 and 400×500 WebP plus a 640×800 JPEG fallback; the original photo is kept in `brand/`. Images below the hero load lazily. First load is now about 140 KB on a phone and 180 KB on a desktop, fonts included.
- [ ] Legal review of the mentions légales and the privacy note (`TODO-LEGAL.md`), including the 3-month retention period for appointment e-mails, to be confirmed by Goundo.

## 9. Then Claude Code

The full build instructions are in `CLAUDE.md`. Claude Code starts with a coherence audit of the brief, `CLAUDE.md` and `index.html`, and stops for approval before building.


- The site is plain static HTML/CSS/JS with no build step, ready for any static host (Netlify, Vercel, GitHub Pages, OVH).
- Steps:
  1. Put `index.html` and `img/` in a repo.
  2. Self-host the fonts from `fonts/` instead of Google Fonts.
  3. Add the mentions légales.
  4. Connect a domain.
- Keep the single-file simplicity unless a blog is added later for SEO.
- Repository layout (decided 28 October 2026): the published website lives in `site/` (`index.html`, `img/`, `fonts/`, later the mentions légales and favicon files). Netlify publishes `site/` only. Everything else (brief, audit, `brand/`, `CLAUDE.md`) stays at the root and is never published.

## 10. Decisions from the coherence audit (28 October 2026)

The owner answered the 22 questions in `AUDIT.md`. Summary, by question number:

1. Handwriting: at most one phrase per block; the hero and "Mes soins" keep both of theirs.
2. "Bienvenue" and "À très vite" tilted −2.5°.
3. The « » around the thesis title: olive.
4. Footer logo 120px; the header logo never shrinks below 120px.
5. CSS tokens keep their English names, with a comment mapping them to the brief's names.
6. "Préparation à la naissance" everywhere.
7. Raised "e" in ordinals ("15e") in all visible text.
8. She does home visits: "Je viens à vous" stays.
9. Variable Instrument Sans, self-hosted.
10. Olive text on mauve poudré uses `#5A613D` (olive-texte); everywhere else olive stays `#5F6640`.
11. Separate `mentions-legales.html`, linked from the footer of both pages.
12. Address in the contact section (« Cabinet : 62 rue des Entrepreneurs, 75015 Paris ») and in the mentions légales, as her cabinet. Phone on neither page (LCEN point tracked in `TODO-LEGAL.md`).
13. Host: Netlify.
14. Domain: goundosakho.fr, used in the canonical link, `og:url`, `sitemap.xml` and `robots.txt`. DNS connection in Phase 7.
15. No better photo yet: best crop of the current one.
16. The accent on "santé" is cut: image kept for now, listed in section 8.
17. Batch approved: unused images moved to `brand/`; no sideways scroll on tablets; `<time>` tags in the timeline become `<span>`; the Mémoire label becomes a heading (same look); the copy button is hidden without JS and announces "Adresse copiée"; the light button keeps its white hover; the urgent line's bold set explicitly to 600.
18. `TODO-LEGAL.md` lists the legal points to review.
19. Checklist item "Le motif de la consultation" becomes "Le type de consultation (grossesse, gynécologie, post-partum…)", followed by the line "Inutile de détailler votre situation par e-mail, on en parlera en consultation."
20. Privacy note: "Les e-mails de prise de rendez-vous sont supprimés au plus tard 3 mois après le rendez-vous." To be confirmed by Goundo and the legal review.
21. "Classée 4e sur 206" stays.
22. Doctolib, when it comes, replaces the header and hero booking buttons; "Écrire un e-mail" stays e-mail.
