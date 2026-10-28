# Legal points to review before launch

Prepared 28 October 2026 from the audit (`AUDIT.md`, findings 16–18 and 29–34) and the owner's answers (`docs/BRIEF-site-goundo.md`, section 10).
**None of this is legal advice.** Each point needs confirmation by Goundo and, where marked, by someone qualified (her Ordre's departmental council, or a lawyer) before the mentions légales go live.

## Missing facts (placeholders on the page until given)

The page is `site/mentions-legales.html` (Phase 4, 28 October 2026). Each item below is a visible `[À COMPLÉTER : …]` on it, except SIRET and credits, which are left out until decided.

- [ ] **RPPS number.** Shown as `[À COMPLÉTER : numéro RPPS]`.
- [ ] **Ordre des sages-femmes:** the departmental council she is registered with. Shown as `[À COMPLÉTER]`.
- [ ] **Netlify's legal details** (exact company name, address, phone number), copied from Netlify's own legal page. The page only says "Netlify" for now; I could not reach Netlify's website from the build environment to copy them.
- [ ] **SIRET number:** not clearly required by the LCEN for a liberal profession that is not on the trade register, but often shown. Does Goundo want it there?
- [ ] **Credits:** does the portrait photographer need to be credited?

## Points to have checked

1. **Phone number.** The owner decided not to show a phone number on either page. LCEN article 6-III (and article 19 for professionals) may require one among the publisher's details. To check: is an e-mail address enough, or is a number required? A separate professional number is an option.
2. **Regulated-profession details** (LCEN article 19). The page should probably show: the professional title (sage-femme) and the state where it was granted (France); the professional body (Ordre des sages-femmes, departmental council); and a reference to the professional rules (code de la santé publique, including the code de déontologie des sages-femmes). Check the exact wording and article references. **On the page now:** "Sage-femme, diplôme obtenu en France (Université Paris Cité)" and "Code de la santé publique, notamment le code de déontologie des sages-femmes (articles R. 4127-301 et suivants)". Both need checking before launch.
3. **Privacy note (RGPD).** Planned content: the site sets no cookies, has no analytics and no form; appointment e-mails are used only to answer the request. It should also give the data controller (Goundo Sakho), the purpose, the legal basis, the retention period, the visitor's rights (access, correction, deletion) and the right to complain to the CNIL. To check: is this complete? **On the page now:** no cookies, analytics or form; e-mails used only to answer the request; Goundo Sakho named as the person responsible; the 3-month deletion; access, correction and deletion by e-mail; complaint to the CNIL. Not on the page: the legal basis, and Google as the e-mail provider (point 5).
4. **Retention period, to confirm by Goundo and the legal review:** "Les e-mails de prise de rendez-vous sont supprimés au plus tard 3 mois après le rendez-vous." Goundo must actually apply it.
5. **Health information by e-mail.** E-mails reach a consumer Gmail account (Google). The checklist now asks only for the *type* of consultation and says not to detail the situation by e-mail. To check: is this enough, and should the privacy note mention Google as the e-mail provider?
6. **Professional communication (code de déontologie).** The page has no testimonials or reviews. The owner kept "classée 4e sur 206" (her PACES ranking). Optionally, Goundo can ask her departmental council to look over the whole page.
7. **Address.** It is shown as her cabinet (she also works elsewhere). To check: is this the professional address that should appear in the mentions légales?

## Before going live

- [ ] No `À COMPLÉTER` left on any page.
- [ ] Points 1–7 above answered.
- [ ] If analytics, a form or a booking widget is ever added, rewrite the privacy note first.
