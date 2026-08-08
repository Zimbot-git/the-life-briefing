# CONTEXT FILE — peteschuil.live umbrella/hub rebuild — 2026-08-07

## BASELINE
KB version / last fulfilment date this session worked against: current as of project files provided in this chat on 2026-08-07 (no other baseline date stated to this session).
Files present at session start: standard 17-file set — 00, 01, 02, 03 (referenced via 04/05 read, not separately opened), 04, 05, 10, 11, 12, 13, 14, 20, 21, 22, 23, 30, 31.

## DECISIONS & CHANGES

### Item 1 — Umbrella identity rebrand approved and built (title, meta, OG, Twitter, JSON-LD, nav wordmark)
- WHAT: Operator approved taking peteschuil.live from LIFE-Briefing-first identity to Pete-Schuil-umbrella identity at every technical level, not just visible body copy. Built and packaged (NOT yet deployed — see Item 7): `<title>` → "Pete Schuil — Pilot, Entrepreneur, Artist, Author"; meta description, `og:description`, `twitter:description` → the approved one-liner from `23` §6 ("Pete Schuil is a Zimbabwean chartered accountant, commercial pilot and artist who has spent half a century building and rescuing businesses across southern Africa — and now shares what he has learned about what lasts."); `og:site_name`/`og:title`/`twitter:title` → "Pete Schuil"; nav wordmark changed from "The LIFE Briefing" to "Pete Schuil" in all four places it appears on the page (main nav, footer, Privacy Policy header, Terms header — the footer occurrence was not caught in the original plan and was found during build); hero eyebrow/kicker line changed from "Living Intentionally for Excellence" to "Pete Schuil · Living Intentionally for Excellence" (hero headline and JOIN CTA below it deliberately left untouched — still the only fully-built, tested conversion flow on the page, and LIFE Briefing is Tier-1/no-revenue-push per the escalation-gate framework, so its proven copy wasn't disturbed).
- SCOPE: shared
- TARGET FILE: 20_PORTFOLIO_MASTER_CONTEXT.md
- OPERATION: replace-in-place
- DETAIL: Update the Web & social presence section's description of the live site's identity/backlog. Current text (as read this session) describes the site as still LIFE-Briefing-first in title/meta/OG/nav with this listed as an open backlog item — that description is now stale. Replace with: site rebuild is built and packaged as of 2026-08-07 to present as a Pete Schuil umbrella identity at title/meta/OG/Twitter/JSON-LD/nav level; NOT yet deployed to the live site (GitHub Pages still serves the prior LIFE-Briefing-first version as of this writing). JSON-LD restructured from a single `ProfessionalService` block into an `@graph` with a `Person` entity (Pete Schuil, `@id":"https://peteschuil.live/#pete"`) and a `ProfessionalService` entity (The LIFE Briefing specifically, linked via `provider`) — this is a new structural decision, not previously specified anywhere in the KB, made because renaming the old single-block schema's `name` field to "Pete Schuil" while keeping a `$4.95/month` priceRange attached would have been factually wrong.
- SOURCE/STATUS/DATE: [Rin direction (point 6, this session) + Claude build | built, not deployed | 2026-08-07]

### Item 2 — Three known site backlog items closed in the build (entity name, role-line, Meet Pete bio)
- WHAT: Three items already flagged as open backlog in `20` (per this session's audit) were corrected in the site build: (a) legal entity name corrected from "Sparks and Flames Enterprises (PVT) Ltd" to "Sparks & Flames Enterprises (PRIVATE) LIMITED" in all 6 locations found on the page — JSON-LD `legalName`, the Business Details block, the footer copyright line, the Privacy Policy intro, the Terms intro, and the Terms IP-ownership clause; (b) role-line badges changed from the live 6-item set ("Accountant, Pilot, Author, Mentor, Coach, Advisor") to the `23` §3-approved 5-item set ("Pilot, Entrepreneur, Artist, Author, Mentor"); (c) "Meet Pete" bio replaced in full with the `23` §6 "Website — the umbrella" bio, used verbatim (5 paragraphs, the "builder" throughline, AfDB/World Bank Group institutions, painting and health-book mentions all now present — none of this existed in the live bio before). NOT yet deployed — see Item 7.
- SCOPE: shared
- TARGET FILE: 20_PORTFOLIO_MASTER_CONTEXT.md
- OPERATION: replace-in-place
- DETAIL: Close these three items in the Web & social presence backlog list; mark each as "corrected in the 2026-08-07 build, pending deploy" rather than "open." Do not mark fully closed until Item 7's deploy is confirmed by the operator in a future session.
- SOURCE/STATUS/DATE: [Rin direction (points 3–5) + 23 §3/§6 verbatim + Claude build | built, not deployed | 2026-08-07]

### Item 3 — TVFMO ecosystem card unblocked, renamed, and linked on the umbrella site
- WHAT: The umbrella site's TVFMO card previously read "Coming soon" under the label "Oil painting prints," with no link of any kind, despite TVFMO Zimbabwe sales being live and the income-first priority. Per operator direction (point 2) this is corrected in the build: badge now reads "Available now"; card renamed to the real brand name "The View From My Office" (operator confirmed this per point 7); whole card is now a live link to `https://wa.me/c/263787948316` (see Item 8); leading image is Plate 19 ("Chimanimanis from a Plane," see Item 9). The memoir card's heading was changed to include a subtitle span ("The View From My Office — Memoirs of a Bush Pilot") to visually distinguish it from the now-identically-named print-business card; operator confirmed the em-dash title form is correct (not the colon form used in casual chat). NOT yet deployed — see Item 7.
- SCOPE: tvfmo
- TARGET FILE: 11_TVFMO_DECISIONS_LOG.md
- OPERATION: append
- DETAIL: Append a dated entry: "2026-08-07 — peteschuil.live umbrella site's TVFMO card corrected from 'Coming soon'/unlinked to 'Available now', renamed 'The View From My Office', linked to the WhatsApp catalog deep-link, built and packaged for deploy. Site build is a separate deliverable from the dedicated Shopify build (see Item 10); this card intentionally does not yet link to shop.peteschuil.live."
- SOURCE/STATUS/DATE: [Rin direction (points 2, 7) + Claude build | built, not deployed | 2026-08-07]

### Item 4 — InnBucks removed from site copy pending test; standing re-enable trigger
- WHAT: Per operator instruction (point 1), InnBucks removed from all 3 places it appeared in customer-facing/legal copy on the live site (subscribe-flow step 2, Privacy Policy payment-information paragraph, Terms subscription-and-billing paragraph) — each edited surgically to read "Paynow or EcoCash" instead of "Paynow, EcoCash or InnBucks." This is consistent with the existing 2026-07-31 standing decision not to feature InnBucks until tested, but this session found it was still live in site copy despite that decision. Operator gave a standing instruction: once InnBucks is tested and confirmed working, Claude should flag it for re-listing on the website, in documents, and "all places where that becomes relevant" — i.e. this is not scoped to the website alone.
- SCOPE: shared
- TARGET FILE: 21_SHARED_DECISIONS_LOG.md
- OPERATION: append
- DETAIL: Append: "2026-08-07 — InnBucks found live in peteschuil.live customer-facing copy (subscribe steps, Privacy Policy, Terms) despite the 2026-07-31 do-not-feature decision; removed in the 2026-08-07 site build (pending deploy, see Item 7). Standing instruction from operator: once an InnBucks account exists and a test payment passes, flag for re-listing across ALL customer-facing surfaces — this website, the TVFMO invoice template, WhatsApp quick-replies, and any other copy — not just the original 2026-07-31 scope." This should also be reflected as an open item (see OPEN ITEMS CHANGED below) so future sessions don't need to rediscover the trigger condition.
- SOURCE/STATUS/DATE: [Rin direction (point 1) | built, not deployed | 2026-08-07]

### Item 5 — New OG share-card image built, replacing the stale asset
- WHAT: The live `og-image.png` had "The LIFE Briefing" wordmark and a "$4.95/month" price pill baked into the pixels, and its declared meta dimensions (1200×630) didn't match its actual file dimensions (900×450). Per operator direction (point 2, "proper redesign"), a new umbrella-appropriate share card was designed and built from scratch: same background photograph (Solitude, the cormorant-on-a-post photo already used as the hero image) and the same brand palette/typography (Fraunces + Inter), but now reads "Pete Schuil" with the approved role-line as the tagline and "peteschuil.live" as a footer tag — no price, no LIFE Briefing-specific wording. Saved as `og-image.jpg` (53KB vs the original 538KB PNG) at the correct 1200×630. `og:image`/`twitter:image` meta tags updated to point at the new filename. NOT yet deployed — see Item 7.
- SCOPE: shared
- TARGET FILE: 20_PORTFOLIO_MASTER_CONTEXT.md
- OPERATION: replace-in-place
- DETAIL: Update the Web & social presence section to note the OG/share-card asset is now `og-image.jpg` (not `.png`), umbrella-branded, correctly dimensioned at 1200×630.
- SOURCE/STATUS/DATE: [Rin direction (point 2) + Claude build | built, not deployed | 2026-08-07]

### Item 6 — Portrait image technical fix (de-duplication)
- WHAT: Found during this session (not previously known to the KB): `pete-portrait.jpg` (548KB) exists as a real file in the repo but was unused — the live page instead embedded a separate ~400KB+ base64-encoded copy of the same portrait directly in the HTML. Fixed in the build: the `<img>` tag now references the real file (`./pete-portrait.jpg`) instead of the inline base64 blob. Combined with the eco-card image fix in Item 3 (also previously base64-inline, now an external file reference), total page weight dropped from 236KB to 52KB.
- SCOPE: shared
- TARGET FILE: 20_PORTFOLIO_MASTER_CONTEXT.md
- OPERATION: replace-in-place
- DETAIL: Note in the site's technical/architecture description that the portrait and TVFMO-card images are external file references, not inline base64, as of the 2026-08-07 build. This also resolves the KB's previously-unclear "self-contained vs modular" architecture question for these two specific elements — confirmed the live (pre-rebuild) site actually used a mix of both approaches, not cleanly one or the other.
- SOURCE/STATUS/DATE: [Claude finding + build | built, not deployed | 2026-08-07]

### Item 7 — Deploy status: none of the above is live yet
- WHAT: All of Items 1–6 are built, verified against source (structural/textual checks — tag balance, JSON-LD validity, every old string confirmed removed, every new string confirmed present), and packaged as a complete, ready-to-push file set (`index.html` + `images/` + `media/tvfmo/TVFMO-19-mockup.png` + `pete-portrait.jpg` + `og-image.jpg` + `CNAME`), delivered to the operator as a zip. **None of it has been pushed to the `Zimbot-git/the-life-briefing` repo or deployed to the live GitHub Pages site.** The live site as of 2026-08-07 is still the pre-rebuild version. Per this project's standing rule, Claude does not push/deploy autonomously — that remains the operator's/Pete's action. Separately, the uploaded reference zip (`the-life-briefing-main_2_.zip`) was confirmed byte-identical to the live GitHub `main` branch `index.html` at session start, confirming no undocumented drift between the repo and the live site at that point.
- SCOPE: shared
- TARGET FILE: 20_PORTFOLIO_MASTER_CONTEXT.md
- OPERATION: replace-in-place
- DETAIL: Any future session must NOT assume Items 1–6 are live until the operator confirms the push/deploy happened. Add this as an explicit open item (see below) rather than closing the backlog items outright.
- SOURCE/STATUS/DATE: [Claude verification | built, packaged, not deployed | 2026-08-07]

### Item 8 — WhatsApp catalog deep-link mechanism identified for TVFMO
- WHAT: `https://wa.me/c/<number, international format, no plus or spaces>` is a documented WhatsApp catalog deep-link format that opens a WhatsApp Business catalog directly. Since the shared WABA (+263 787 948 316) has exactly one catalog attached to it (the TVFMO catalog), `https://wa.me/c/263787948316` was used as the TVFMO umbrella-card link (Item 3) with no router-bot build required. Source was a third-party BSP documentation page, not Meta's own docs — Claude explicitly recommended the operator or Pete personally click-test this link on a phone once deployed, before relying on it.
- SCOPE: tvfmo
- TARGET FILE: 11_TVFMO_DECISIONS_LOG.md
- OPERATION: append
- DETAIL: Append: "2026-08-07 — wa.me/c/<number> WhatsApp catalog deep-link identified and used as the umbrella-site TVFMO CTA (https://wa.me/c/263787948316). [re-verify] — sourced from third-party BSP docs, not Meta's own; needs a live click-test by Pete/operator once the site is deployed, since this WABA's catalog behaviour hasn't been confirmed via this specific link format before."
- SOURCE/STATUS/DATE: [Claude research (web_search) | re-verify — untested live | 2026-08-07]

### Item 9 — Plate 19 mockup confirmed live and genuine
- WHAT: Plate 19 ("Chimanimanis from a Plane" — the painting behind the TVFMO origin story) is one of six plates (03, 06, 08, 12, 19, 20) the KB previously flagged as blocked on hi-res TIFF source, with an explicitly unresolved contradiction (11_TVFMO_DECISIONS_LOG, 2026-07-31 entry) about whether these six were genuinely held back or live with placeholder images. This session fetched `TVFMO-19-mockup.png` directly from the repo and visually inspected it: HTTP 200, 1.1MB, 1920×1920px, a real finished lifestyle mockup (signed canvas, "Pete Schuil '25," staged above a sofa) — not a placeholder. This resolves the contradiction FOR PLATE 19 SPECIFICALLY as of 2026-08-07. The other five plates in that blocked list (03, 06, 08, 12, 20) were NOT checked this session and remain in their prior unresolved state — do not generalise this finding to all six.
- SCOPE: tvfmo
- TARGET FILE: 11_TVFMO_DECISIONS_LOG.md
- OPERATION: append
- DETAIL: Append: "2026-08-07 — Plate 19 (Chimanimanis from a Plane) mockup verified live and genuine by direct fetch + visual inspection (not a placeholder), partially resolving the 2026-07-31 six-plate contradiction. Plates 03, 06, 08, 12, and 20 remain unverified/unresolved — this finding does not extend to them." Also update the per-plate status table (if one exists in 13_TVFMO_CATALOGUE_ASSETS.md — not opened this session, flagging for the fulfilment session to check) to reflect Plate 19's confirmed-live status specifically.
- SOURCE/STATUS/DATE: [Claude direct verification (fetch + visual inspection) | confirmed | 2026-08-07]

### Item 10 — Shopify account created and funded for pete@peteschuil.live
- WHAT: Per operator (point 8): a Shopify account under pete@peteschuil.live was created 2026-08-07, the card has been loaded with funds, and the Basic Plan promotional rate ($3/month) has been activated for 3 months (through November 2026). This resolves the prior blocked state recorded in `11_TVFMO_DECISIONS_LOG` ("Shopify store access blocked — trial expired, no funds on card"). The actual Shopify store build (theme, products, shop.peteschuil.live domain connection) is explicitly out of scope for this chat and will happen in a separate, dedicated chat. The peteschuil.live umbrella site's TVFMO card does NOT link to shop.peteschuil.live yet (see Item 3) — that will be a follow-up edit once the dedicated build is live.
- SCOPE: tvfmo
- TARGET FILE: 10_TVFMO_MASTER_CONTEXT.md
- OPERATION: replace-in-place
- DETAIL: Update the Shopify/international-fulfilment status line from "blocked — trial expired, no funds on card" to "account created and funded 2026-08-07 (pete@peteschuil.live), Basic Plan active through ~November 2026; store build itself not started, scheduled for a dedicated separate chat." Also append the dated fact to `11_TVFMO_DECISIONS_LOG.md` as a second, separate append operation, since master-context (current state) and decisions-log (dated event) are both legitimately updated by this one underlying fact per this KB's established pattern.
- SOURCE/STATUS/DATE: [Rin direction (point 8) | confirmed | 2026-08-07]

### Item 11 — Meta Business Verification re-verify risk on identity rebrand — operator accepted
- WHAT: This session's audit flagged that peteschuil.live's Meta Business Verification (approved 2026-07-24) was reviewed against the site "in its current wider form" — i.e. the LIFE-Briefing-first identity being replaced by Item 1. Claude flagged this as an open re-verify question rather than asserting either way. Operator's response (point 6): "I don't think this will affect Meta verification, and if it does, it should be easy" — an explicit editorial risk-acceptance, not a resolution of the underlying technical question. The question of whether Meta actually requires re-verification after this identity change remains genuinely unconfirmed.
- SCOPE: shared
- TARGET FILE: 21_SHARED_DECISIONS_LOG.md
- OPERATION: append
- DETAIL: Append: "2026-08-07 — Operator accepted the risk that the peteschuil.live identity-level rebrand (title/OG/nav from LIFE-Briefing-first to Pete-Schuil-umbrella) might require Meta Business Verification re-review; judged low-risk and proceeded. Not independently verified with Meta. Flag for a Meta Business Manager check once the site is deployed and if any verification-status issue appears."
- SOURCE/STATUS/DATE: [Rin editorial judgement | accepted risk, unverified | 2026-08-07]

## NEW FILES REQUESTED (if any)
None. No distinct, durable new body of knowledge was created this session — everything above extends existing files' scope (site content, TVFMO status, shared decisions).

## SUPERSEDED VALUES (rot signatures to register)
- "The LIFE Briefing with Pete Schuil" (site `<title>`/`og:site_name`/nav wordmark) → "Pete Schuil" (umbrella identity) → flagging for the shared/portfolio supersession registry; unclear to this session whether that lives in `05_GLOSSARY.md` (LIFE-Briefing-scoped) or should be a new shared registry entry — fulfilment session to judge, since no dedicated shared (`2x`) glossary file currently exists.
- "Sparks and Flames Enterprises (PVT) Ltd" → "Sparks & Flames Enterprises (PRIVATE) LIMITED" — this rot-signature likely already exists from the 2026-07-26 correction (`21_SHARED_DECISIONS_LOG`); this session only changes its STATUS from "not yet applied to the live site" to "applied in the 2026-08-07 build, pending deploy." Do not create a duplicate registry entry — update the existing one's status if the schema supports it.
- Live TVFMO card state "Coming soon" (unlinked) → "Available now" (linked to WhatsApp catalog) → 11_TVFMO_DECISIONS_LOG.md.
- `og-image.png` (900×450, LIFE-Briefing-branded) → `og-image.jpg` (1200×630, umbrella-branded) → 20_PORTFOLIO_MASTER_CONTEXT.md asset registry, if one exists.

## OPEN ITEMS CHANGED
- OPENED — "Deploy the 2026-08-07 peteschuil.live rebuild (push to Zimbot-git/the-life-briefing, confirm GitHub Pages serves it)" — owned by 20_PORTFOLIO_MASTER_CONTEXT.md. Nothing in Items 1–6 should be treated as live until this closes.
- OPENED — "Live-browser visual QA of the 2026-08-07 rebuild once deployed" — owned by 20_PORTFOLIO_MASTER_CONTEXT.md. This session could only verify the hero section visually (sandbox rendering-tool limitation, see CONTRADICTIONS below); everything else was verified structurally/textually only, not visually.
- OPENED — "Click-test the wa.me/c/263787948316 WhatsApp catalog link live on a phone" — owned by 11_TVFMO_DECISIONS_LOG.md.
- OPENED — "Re-flag InnBucks for re-listing across all customer-facing surfaces (site, TVFMO invoice template, WhatsApp quick-replies, etc.) once an account exists and a test payment passes" — owned by 21_SHARED_DECISIONS_LOG.md — standing trigger, not time-bound.
- OPENED — "Point the TVFMO umbrella-site card at shop.peteschuil.live once the dedicated Shopify build (separate chat) goes live" — owned by 11_TVFMO_DECISIONS_LOG.md.
- REWORDED (narrowed) — the six-plate hi-res-blocked open item now excludes Plate 19 specifically (confirmed live/genuine) and applies only to plates 03, 06, 08, 12, 20 — owned by 11_TVFMO_DECISIONS_LOG.md / 13_TVFMO_CATALOGUE_ASSETS.md.
- CLOSED (pending deploy — do not fully close until Item 7 resolves) — the three site backlog items from Item 2 (entity name, role-line, Meet Pete bio) and the InnBucks-in-copy issue from Item 4.

## CONTRADICTIONS / FLAGS FOR OPERATOR
- **Footer tagline left unchanged.** The footer still reads "Living Intentionally for Excellence" directly under the new "Pete Schuil" wordmark — this is LIFE Briefing's own tagline (the LIFE acronym), not a generic Pete Schuil motto. Claude judged this an acceptable minimal-scope decision (the footer's second line already correctly attributes it to the LIFE Briefing product specifically), but it was not explicitly reviewed by the operator and may be worth a future pass if the footer should broaden to match the rest of the umbrella rebrand.
- **Visual QA is incomplete.** The sandbox's only available rendering tool (an old WebKit-based utility) could reliably render only the page's first viewport (hero section — confirmed pixel-correct) and went blank on everything below the fold regardless of technique tried. No JS, scroll-reveal animation, or hidden-by-default CSS was found in the source that would explain this, so it's judged a tooling limitation, not a file defect — but this is judgement, not proof. Recommend a real-browser check before or immediately after deploy.
- **Meta Business Verification re-verify question remains genuinely open** (see Item 11) — operator accepted the risk but the underlying technical question ("does Meta actually require re-review after this kind of identity change") was not independently confirmed by Claude or by Meta's own documentation this session.
- **Entity-name/identity rot-signature routing is uncertain** (see SUPERSEDED VALUES above) — this session could not confirm whether `05_GLOSSARY.md` is the correct registry for shared/portfolio-wide (not LIFE-Briefing-specific) rot signatures, since no dedicated `2x`-numbered glossary file exists in the current KB structure. Fulfilment session should resolve or flag back.

## END CONTEXT FILE
