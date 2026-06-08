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

## B. Resolve open decisions (next 1-2 sessions)

These need WELI rulings before product work makes sense. Listed in deadline order.

- [ ] **B1. SHP-016 (new).** Confirm `shop.wildwoohoo.com` (this scaffold) is the canonical shop surface, OR re-align the strategy doc to also use the subdomain, OR keep the original `wildwoohoo.com.au` plan and treat this scaffold as the landing while a separate Shopify domain handles checkout. The main site already links the subdomain, so subdomain wins by default. Just needs sign-off.
- [ ] **B2. SHP-005.** Bookkeeping platform (Wave / Xero / MYOB). Deadline 2026-07-15.
- [ ] **B3. SHP-004.** GST registration timing. Deadline 2026-07-31.
- [ ] **B4. SHP-007.** Email platform (Buttondown recommended). Before first newsletter.
- [ ] **B5. SHP-013.** Returns policy (30-day standard recommended). Before shop opens.
- [ ] **B6. SHP-006.** EU shipping policy v1 (POD-only EU recommended). Before first international sale.
- [ ] **B7.** Decide e-commerce backend: stick with Shopify Basic per strategy doc, or revisit. The strategy doc's reasoning (mixed inventory, GST mechanics, time-to-launch) still holds. The static scaffold in this repo can sit in front of a Shopify checkout via a Shopify Buy Button + cart integration, or migrate fully to a Shopify-themed storefront.

## C. Visual + identity polish on this scaffold (next session)

Small, low-risk polish that improves how the placeholder shop looks while products are being built.

- [ ] **C1.** Replace the `W` text chip in the header with the actual WildWooHoo brand chip image (`wwh-chip-green.png` from the main site repo). Copy into `assets/img/` and update the `index.html` + four category pages + 404 + product template.
- [ ] **C2.** Add a favicon set under `assets/img/` and reference from each HTML head. Source from main site (`favicon.ico`, `favicon-16.png`, `favicon-32.png`, `apple-touch-icon.png`).
- [ ] **C3.** Add an Open Graph image at `assets/img/og-shop.png` (1200x630) and reference from every page's `og:image` meta. Coordinate with the main site's `og-card.png` aesthetic.
- [ ] **C4.** Consider adding the language switcher used on the main site (Google Translate dropdown). Brief lifted from `wildwoohoo.com/index.html` line 84-100.
- [ ] **C5.** Add a brief one-line "Opening Q3 2026 — digital downloads first" status banner to the top of `index.html` for visitors who land before the catalogue exists.

## D. First product work (when WELI is ready, 2026-Q3)

The strategy doc opens the shop with two digital products in Q3 2026.

- [ ] **D1.** Write copy for `categories/educational/kangaroo-time-classroom-kit/index.html`. AU$25-35, digital. Source content lives at `~/Studio/Projects-In-The-Site/Kangaroo-Time-Workshop/` and related Kangaroo Time material.
- [ ] **D2.** Write copy for `categories/educational/kangaroo-time-stems-pack/index.html`. AU$25-45, digital. Stems sourced from the Kangaroo Time master at `~/Studio/Websites/WildWooHooDotCom/Kangaroo Time (Instrumental)_24 Bit 44.1 Master.wav` plus separated stems.
- [ ] **D3.** Both need full editorial chain (writer → reviewer → chief-editor) before publish.
- [ ] **D4.** Commission product imagery (per Insight 33: no stock photos). Brief in the product-template README.
- [ ] **D5.** Wire a payment + fulfillment path. Shopify Buy Button is the lightest-weight option that keeps this repo static; full Shopify storefront migration is the strategic option per the strategy doc.

## E. Future surfaces (2026-Q4 and 2027)

Track here so they don't get lost.

- [ ] **E1.** POD merch baseline goes live (Q4 2026). 5 SKUs. Printful AU + product templates.
- [ ] **E2.** Books-companion PWA (Q1 2027). Lives at `companion.wildwoohoo.com` (separate repo), not in this one. Sold from `/categories/tools/`.
- [ ] **E3.** Ebook book 1 (Q1 2027). Sold from `/categories/childrens-books/`.
- [ ] **E4.** First limited drop (Q1 2027). Concept work, design pass, drop landing page under `/categories/merch/drop-01-[name]/`.
- [ ] **E5.** Trade paperback book 1 (Q2 2027). With companion-app unlock code printed in back cover.
- [ ] **E6.** Drop cadence from Q1 2027: one drop per quarter, numbered, no re-press.

## F. Children's-book session split

Per strategy doc §5, the children's-book content (title, illustrator, narrative arc, publisher decision) needs its own session. Brief skeleton:

- [ ] **F1.** Draft `~/Studio/Strategy-Hub-2026/01_WildWooHoo-Studio/CHILDRENS-BOOK-SESSION-BRIEF.md`. Initial-context-to-load list from strategy doc §5.4.
- [ ] **F2.** Schedule the session for 2026-09-15 (after shop infrastructure operational).
- [ ] **F3.** That session's deliverables: title backlog, sample chapter, illustrator partner, narrative arc, publisher decision, production budget, ICIP discipline confirmation.

## G. Strategy + admin maintenance

- [ ] **G1.** Re-base the strategy doc on WELI redlines once they happen. Insert §20 and §21 into `_LOCKED-DECISIONS-2026-06-04.md` per protocol.
- [ ] **G2.** Update `STRATEGY-SUMMARY.md` in this repo whenever the strategy doc updates materially.
- [ ] **G3.** Update `sitemap.xml` whenever new products or pages get added.
- [ ] **G4.** Confirm whether `wildwoohoo.com.au` is registered to WELI's ABN. If yes, decide whether it points at the same shop or sits as a future option.

## H. Things that are intentionally NOT on this list

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

1. **Run steps A1-A7** above (deploy this scaffold to shop.wildwoohoo.com). Half a session of WELI's time, mostly waiting on DNS propagation.
2. **Resolve B1** (confirm subdomain is canonical) and **B7** (e-commerce backend decision, even if "yes, Shopify Basic, but not yet").
3. **Run C1-C3** (replace text chip with brand chip image, add favicons, add OG image). Small polish, makes the placeholder feel less placeholder.
