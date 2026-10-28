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
| papier | `#F7F0F2` | Page background, used instead of white |
| encre | `#3A2430` | Body text |
| encre-douce | `#6E5762` | Secondary text |
| nacre | `#F7EEF1` | Text on mûre or olive |
| nacre-douce | `#D9C2CB` | Secondary text on mûre |

Proportions are roughly 60% light (mauve poudré or papier), 30% mûre and 10% olive. The site is deliberately light-theme only, a branded look rather than a dark-mode-aware one.

### Type

- **Gloock** for headings: one weight, never bold or italic.
- **Instrument Sans** for body text, weights 400 to 600.
- Labels are small caps in olive, 12.5px, letter-spacing 0.14em, uppercase.
- If Gloock ever has to be replaced (Canva), use **DM Serif Display**.

### Logo

The word "Goundo" in a thin line with droplet terminals. It comes in mûre, mauve poudré, olive and mauve, as transparent PNGs. The line is very thin, so never display it under about 120px wide.

### Her handwriting: the signature of the brand

These are real phrases written by Goundo, cut out as transparent PNGs in `img/`:

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

1. At most one handwritten phrase per section. It is a margin note, never the headline.
2. Always pair it with printed text that carries the actual information.
3. Use mûre or olive on light backgrounds and the mauve-poudré (`-blush`) version on dark ones.
4. Tilt it slightly (−2 to −3°).
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
   - Préparation à l'accouchement.
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
   - a "Dans votre message" checklist, styled as a page from her notebook taped onto the mûre band: papier card tilted 1.5°, a strip of mauve-poudré tape, a mauve margin rule, ruled lines and empty olive tick boxes;
   - an urgent-care line: "appelez le 15", inside the note on a mauve-poudré strip, with "15" in a mûre circle.
9. **Footer**: logo, name and LinkedIn (the only social link she wants).

## 5. Motion (already built; keep it restrained)

- **On load (hero):** "Bienvenue" writes itself in (clip-path wipe) while the H1, lead text, buttons and facts rise in sequence. The mauve slab slides up and the photo unveils from the bottom with a slow zoom-out. The "À chaque étape" note drops in, then floats very slightly.
- **On scroll:** this uses CSS scroll-driven animations (`animation-timeline: view()`), wrapped in `@supports`, so Firefox shows a static page. Labels, headings and paragraphs rise into place, list items are staggered, and every handwritten note "writes" itself in. The timeline line draws downward and its dots pop in.
- **Line icons:** each icon draws itself stroke by stroke (stroke-dashoffset), then its droplet dot pops in. The hero facts also write their text in from left to right. Triggered by an IntersectionObserver, so it also works in Firefox. On load the hero facts wait until "Bienvenue" has written itself; reached later by scrolling, they draw at once.
- **On hover:** button arrows nudge forward, service icon badges tilt slightly, service titles shift right, chips turn mûre, and nav links get an underline that draws in.
- Everything is turned off under `prefers-reduced-motion`.

## 6. Real contact details (from her business card)

- Email: **pro.goundo@gmail.com**. The site still shows the placeholder `contact@exemple.fr`, set in one JS constant `EMAIL` plus the visible text.
- Phone: **07 66 96 67 81**. Not on the site yet; ask her whether she wants it there.
- Practice address: **62 rue des Entrepreneurs, 75015 Paris**. Not on the site yet.
- LinkedIn: https://www.linkedin.com/in/goundo-sakho-4746551a8/
- Doctolib: not set up yet. All "Prendre rendez-vous" buttons should switch to Doctolib when she has a link.

## 7. Hard constraints (do not break)

- **No patient testimonials or Google reviews on the site.** The French code of ethics for midwives (*code de déontologie des sages-femmes*) forbids third-party testimonials in professional communication. A plain "Voir sur Google" link to her listing is the safe alternative.
- **No hidden keywords or paid placement.** She wondered about showing up for "sage-femme noire". The honest route is her photo front and center, accurate alt text, and real articles later, for example on care for Black women and representation in perinatal health.
- **Accuracy on health and fees.** Do not invent services, prices or reimbursement rules. A systematic €10 supplement (*dépassement d'honoraires*) on reimbursed sessions may not be allowed for a *conventionnée* midwife. She was told to check with her CPAM or the Ordre before publishing any fee.
- Keep the site in French, single page, and simple.

## 8. Open items to settle in the tune-up

- [ ] Replace the placeholder email with pro.goundo@gmail.com, and decide whether to show the phone number and address.
- [ ] Have Goundo review the copy I wrote in her voice, especially:
  - the bio sentence "on soigne mieux quand on prend le temps d'écouter";
  - "Je viens à vous" next to post-partum, which implies home visits; confirm she does them.
- [ ] Mémoire: add the PDF or the HAL-Dumas link once it is published.
- [ ] Doctolib link, when available.
- [ ] Practical info: opening hours, access (nearest metro), whether she is *conventionnée*, and a sentence on reimbursement once confirmed.
- [ ] Optional: a "Préparation à la naissance" detail. A branded PDF of her 7-session programme exists: anatomie, travail et accouchement, gestion de la douleur, allaitement, soins de puériculture, post-partum, and a 7th theme still to be confirmed.
- [ ] Legally required **mentions légales** page or section: identity, RPPS number, address, hosting provider. Add a privacy note if any form or analytics is added.
- [ ] Favicon, social share image (OG), meta description check, image compression (WebP), and self-hosted fonts.

## 9. Then Claude Code

The full build instructions are in `CLAUDE.md`. Claude Code starts with a coherence audit of the brief, `CLAUDE.md` and `index.html`, and stops for approval before building.


- The site is plain static HTML/CSS/JS with no build step, ready for any static host (Netlify, Vercel, GitHub Pages, OVH).
- Steps:
  1. Put `index.html` and `img/` in a repo.
  2. Self-host the fonts from `fonts/` instead of Google Fonts.
  3. Add the mentions légales.
  4. Connect a domain.
- Keep the single-file simplicity unless a blog is added later for SEO.
