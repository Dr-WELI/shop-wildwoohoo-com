# Shop TODO

Concrete next-session steps. Ordered loosely by sequence and priority. Cross-references the 15 open decisions in `STRATEGY-SUMMARY.md` where applicable.

## A. Deploy this scaffold (this week)

These are the steps WELI runs after this session lands.

- [ ] **A1.** Decide GitHub repo name (`shop-wildwoohoo-com` recommended). Default if no change is made: `shop-wildwoohoo-com`.
- [ ] **A2.** Create the GitHub repo (steps in `README.md` §1).
- [ ] **A3.** Push this local repo to GitHub (steps in `README.md` §2).
- [ ] **A4.** Configure GitHub Pages with custom domain `shop.wildwoohoo.com` and enforce HTTPS (steps in `README.md` §3).
- [ ] **A5.** Add CNAME record `shop` → `dr-weli.github.io` at the DNS provider for `wildwoohoo.com` (steps in `README.md` §4).
- [ ] **A6.** Verify shop.wildwoohoo.com serves the landing page. Check 404 page by visiting a nonsense URL.
- [ ] **A7.** Verify the link from the main site (`wildwoohoo.com` nav and footer both link to `https://shop.wildwoohoo.com`) lands cleanly.

## B. Phase 1 backend setup (Q3 2026 launch, lean path)

The lean phased plan in `STRATEGY-SUMMARY.md` opens with Lemon Squeezy on this static scaffold. Setup is light.

- [ ] **B1.** Create a Lemon Squeezy account at lemonsqueezy.com (free). Verify identity, link a payout bank account.
- [ ] **B2.** In Lemon Squeezy, create the store (`WildWooHoo Studio`), set AUD as the default currency, set tax mode to "I want Lemon Squeezy to handle tax" (MoR mode).
- [ ] **B3.** Generate buy button embed code for each product. Lemon Squeezy gives you a `<script>` tag plus a `<a>` link with class `lemonsqueezy-button`.
- [ ] **B4.** Embed the buy button in `categories/educational/kangaroo-time-classroom-kit/index.html` and the matching stems-pack page (when those product pages exist, see Section D).

## C. Resolve open strategic decisions (1-2 sessions)

These need WELI rulings. Listed in deadline order.

- [ ] **C1. SHP-016 (new).** Confirm `shop.wildwoohoo.com` (this scaffold) is the canonical shop surface, OR re-align the strategy doc to also use the subdomain, OR keep the original `wildwoohoo.com.au` plan and treat this scaffold as the landing while a separate Shopify domain handles checkout. The main site already links the subdomain, so subdomain wins by default. Just needs sign-off.
- [ ] **C2. SHP-013.** Returns policy. 30-day standard recommended (Lemon Squeezy handles digital refunds natively). Before shop opens.
- [ ] **C3. SHP-006.** EU shipping policy. Phase 1 is digital only, so EU is unconstrained. Decision deferred to Phase 2 when POD merch starts.
- [ ] **C4. SHP-004.** GST registration timing. Phase 1 uses Lemon Squeezy MoR posture (they remit GST on your sales), so this decision is **deferred** until Phase 2 or until AU$75K threshold approaches from non-Lemon-Squeezy income.
- [ ] **C5. SHP-005.** Bookkeeping platform (Wave / Xero / MYOB). Wave is fine through Phase 1; Xero becomes worth the cost in Phase 2 when multi-currency starts. Deadline 2026-07-15.
- [ ] **C6. SHP-007.** Email platform. Defer until first 50 newsletter subscribers want it. Then Buttondown.

## D. Visual + identity polish on this scaffold (next session)

Small, low-risk polish that improves how the placeholder shop looks while products are being built.

- [ ] **D1.** Replace the `W` text chip in the header with the actual WildWooHoo brand chip image (`wwh-chip-green.png` from the main site repo). Copy into `assets/img/` and update the `index.html` + four category pages + 404 + product template.
- [ ] **D2.** Add a favicon set under `assets/img/` and reference from each HTML head. Source from main site (`favicon.ico`, `favicon-16.png`, `favicon-32.png`, `apple-touch-icon.png`).
- [ ] **D3.** Add an Open Graph image at `assets/img/og-shop.png` (1200x630) and reference from every page's `og:image` meta. Coordinate with the main site's `og-card.png` aesthetic.
- [ ] **D4.** Consider adding the language switcher used on the main site (Google Translate dropdown). Brief lifted from `wildwoohoo.com/index.html` line 84-100.
- [ ] **D5.** Add a brief one-line "Opening Q3 2026, digital downloads first" status banner to the top of `index.html` for visitors who land before the catalogue exists.

## E. First product work (when WELI is ready, 2026-Q3)

The lean plan opens with two digital products in Q3 2026.

- [ ] **E1.** Write copy for `categories/educational/kangaroo-time-classroom-kit/index.html`. AU$25-35, digital. Source content lives at `~/Studio/Projects-In-The-Site/Kangaroo-Time-Workshop/` and related Kangaroo Time material.
- [ ] **E2.** Write copy for `categories/educational/kangaroo-time-stems-pack/index.html`. AU$25-45, digital. Stems sourced from the Kangaroo Time master at `~/Studio/Websites/WildWooHooDotCom/Kangaroo Time (Instrumental)_24 Bit 44.1 Master.wav` plus separated stems.
- [ ] **E3.** Both need full editorial chain (writer -> reviewer -> chief-editor) before publish.
- [ ] **E4.** Commission product imagery (per Insight 33: no stock photos). Brief in the product-template README.
- [ ] **E5.** Embed the Lemon Squeezy buy button on each product page (per B3 above). Test the checkout flow end-to-end with a small live transaction.

## F. Phase 2 transition (2026-Q4): add POD merch

- [ ] **F1.** Sign up for Shopify Lite at AU$9/mo. Create the Shopify store at `wildwoohoo.myshopify.com`.
- [ ] **F2.** Connect Printful Australia (Brisbane) in the Shopify dashboard. Set up Stanley/Stella STTU755 as the tee base, plus hoodie + tote + poster + sticker.
- [ ] **F3.** Generate Shopify Buy Buttons for each product. Replace the placeholder cards on `/categories/merch/index.html` with the Buy Button embeds.
- [ ] **F4.** Decide GST registration timing (SHP-004). When merch starts selling, the MoR shelter from Lemon Squeezy doesn't apply, so this decision becomes live.
- [ ] **F5.** Set returns policy on the merch product pages (SHP-013).
- [ ] **F6.** Set EU shipping posture (SHP-006). Recommendation: POD-only EU through Printful EU as RP.

## G. Future surfaces (2027)

Track here so they don't get lost.

- [ ] **G1.** Books-companion PWA (Q1 2027). Lives at `companion.wildwoohoo.com` (separate repo), not in this one. Sold from `/categories/tools/`.
- [ ] **G2.** Ebook book 1 (Q1 2027). Sold from `/categories/childrens-books/`.
- [ ] **G3.** First limited drop (Q1 2027). Concept work, design pass, drop landing page under `/categories/merch/drop-01-[name]/`. **First moment inventory matters.** Holding capital ~AU$3-5K per drop.
- [ ] **G4.** Trade paperback book 1 (Q2 2027). With companion-app unlock code printed in back cover.
- [ ] **G5.** Drop cadence from Q1 2027: one drop per quarter, numbered, no re-press.
- [ ] **G6.** Evaluate Shopify Basic migration trigger: >15 SKUs / live drops / AU$3K/month revenue. See Phase 3 in `STRATEGY-SUMMARY.md`.

## H. Children's-book session split

Per strategy doc §5, the children's-book content (title, illustrator, narrative arc, publisher decision) needs its own session. Brief skeleton:

- [ ] **H1.** Draft `~/Studio/Strategy-Hub-2026/01_WildWooHoo-Studio/CHILDRENS-BOOK-SESSION-BRIEF.md`. Initial-context-to-load list from strategy doc §5.4.
- [ ] **H2.** Schedule the session for 2026-09-15 (after shop infrastructure operational).
- [ ] **H3.** That session's deliverables: title backlog, sample chapter, illustrator partner, narrative arc, publisher decision, production budget, ICIP discipline confirmation.

## I. Strategy + admin maintenance

- [ ] **I1.** Re-base the strategy doc on WELI redlines once they happen. Insert §20 and §21 into `_LOCKED-DECISIONS-2026-06-04.md` per protocol.
- [ ] **I2.** Update `STRATEGY-SUMMARY.md` in this repo whenever the strategy doc updates materially.
- [ ] **I3.** Update `sitemap.xml` whenever new products or pages get added.
- [ ] **I4.** Confirm whether `wildwoohoo.com.au` is registered to WELI's ABN. If yes, decide whether it points at the same shop or sits as a future option.

## J. Things that are intentionally NOT on this list

- Building the `wildwoohoo-shop` management-layer app (lives in `~/Code/wildwoohoo-shop/`, its own session).
- Building the books-companion PWA (lives in `~/Code/wildwoohoo-books-companion/`, its own session).
- Music releases on Bandcamp (separate session, M&E surface).
- Sync EPK page on the main site (separate session, M&E surface).
- Grant applications carrying shop revenue case (Funding-Grants session).
- Programmes strategic plan (PRG_SP session).
- Apps roadmap detail (APP_SP session).
- Brand-Position v2 update (next-sweep work per Locked §18.3).

## Quick wins for the very next session

Three concrete things to do in the FOLLOWING session, ranked:

1. **Finish A** (DNS + Pages verification). The push has happened; you only need to add the CNAME record at your registrar and wait for HTTPS to provision. Half a session, mostly waiting.
2. **Run B1-B3** (Lemon Squeezy account + store + buy buttons). Phase 1 backend is set up. No products to sell yet, but the path is wired.
3. **Run D1-D3** (replace text chip with brand chip image, add favicons, add OG image). Small polish that makes the placeholder feel less placeholder.
