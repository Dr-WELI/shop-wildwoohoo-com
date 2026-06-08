# WildWooHooShop

The repository for **shop.wildwoohoo.com**, the online shop for WildWooHoo Studio.

This is a static-site scaffold: HTML, CSS, no build step, deployed via GitHub Pages. Products will fill in later. For now the shop is an opening-soon landing surface with four category placeholders, a product page template, and the brand visual system inherited from the main site.

- **Main site:** [wildwoohoo.com](https://wildwoohoo.com)
- **Shop domain:** shop.wildwoohoo.com (this repo)
- **Owner:** Dr WELI / WildWooHoo Studio (ABN 61 239 662 726)
- **Built:** 2026-06-08

## What this is

A home for shop products to live in. The infrastructure is up; the products are not. When products land, they get added as product pages cloned from `_template/product-page.html` under the appropriate `/categories/` folder.

This repo is intentionally minimal:
- No e-commerce backend yet (no Stripe, no Snipcart, no Shopify integration). The strategy doc proposes Shopify Basic at decision time; until then, this is a static scaffold with hooks for a backend to be wired in.
- No analytics pixels yet. GA4 / Meta Pixel / TikTok Pixel / Plausible get added at backend-migration time.
- No real products yet. Categories show "coming soon" with the strategy-doc ship dates.

## Repo layout

```
WildWooHooShop/
├── CNAME                                shop.wildwoohoo.com (GitHub Pages domain)
├── .nojekyll                            tells GitHub Pages skip Jekyll
├── .gitignore
├── README.md                            this file
├── STRATEGY-SUMMARY.md                  distilled shop strategy for future sessions
├── TODO.md                              concrete next-session steps
├── index.html                           shop landing page
├── 404.html                             graceful not-found
├── robots.txt
├── sitemap.xml
├── css/
│   ├── wwh-brand-tokens.css             copied from main site, single source lives there
│   └── shop.css                         shop-local stylesheet (self-contained)
├── assets/
│   └── img/                             product images go here, one folder per product
├── categories/
│   ├── childrens-books/index.html       category placeholder
│   ├── educational/index.html           category placeholder
│   ├── merch/index.html                 category placeholder
│   └── tools/index.html                 category placeholder
└── _template/
    ├── product-page.html                clone for each new product
    └── README.md                        how to clone and fill in
```

## DNS + GitHub setup steps for WELI

These steps haven't run yet. Run them in order. Each step is independent of the others except where noted.

### 1. Create the GitHub repo

1. Log in to GitHub as `Dr-WELI` (or whichever account owns the main-site repo).
2. Create a new public repo named `shop-wildwoohoo-com` (or whatever name you prefer).
3. Do NOT initialise with a README, .gitignore, or licence on GitHub. The local repo already has what it needs.

### 2. Push the local repo to GitHub

From this folder (`~/Studio/Websites/WildWooHooShop/`):

```bash
cd ~/Studio/Websites/WildWooHooShop
git init
git add .
git commit -m "Initial commit: shop scaffold"
git branch -M main
git remote add origin https://github.com/Dr-WELI/shop-wildwoohoo-com.git
git push -u origin main
```

(Replace `Dr-WELI` and `shop-wildwoohoo-com` with the actual GitHub account and repo name if different.)

### 3. Configure GitHub Pages

1. On the new GitHub repo, go to **Settings** → **Pages**.
2. Under **Build and deployment**:
   - **Source:** Deploy from a branch
   - **Branch:** `main` / `/ (root)`
   - Save.
3. Under **Custom domain**, enter `shop.wildwoohoo.com` and save.
4. Tick **Enforce HTTPS** once GitHub finishes provisioning the certificate. This can take 15-30 minutes after the DNS change in step 4 propagates.

### 4. Add the DNS record at the registrar where wildwoohoo.com lives

1. Log in to the DNS provider that hosts `wildwoohoo.com` (this is wherever the main-site nameservers point; check at https://www.whois.com if you're not sure).
2. Add a **CNAME** record:
   - **Host / Name:** `shop`
   - **Value / Points to:** `dr-weli.github.io` (lower-case, GitHub's username; replace if the GitHub account is different)
   - **TTL:** automatic / default
3. Save. DNS propagation typically takes 5 to 60 minutes.

### 5. Verify the shop is live

From any browser:

```
https://shop.wildwoohoo.com
```

Should serve the shop landing page. If you see a 404 for ~5 minutes after step 4, give it time. If you still see a 404 after 30 minutes, check that the CNAME record points to `dr-weli.github.io` (no trailing dot needed in most providers), and that GitHub Pages settings show the custom domain saved.

## How to add a new product (later, when products exist)

1. Pick the category: `childrens-books`, `educational`, `merch`, or `tools`.
2. Clone `_template/product-page.html` into `/categories/[category]/[product-slug]/index.html`.
3. Replace every `REPLACE-ME` placeholder.
4. Drop seven product images into `/assets/img/[product-slug]/`.
5. Add the URL + today's date to `/sitemap.xml`.
6. Add a product card to the category's `index.html` so the product is discoverable from the category page.
7. Full editorial chain (writer → reviewer → chief-editor) before pushing.

See `_template/README.md` for the data-field schema and shop-immersion-derived rules (Insights 4, 5, 6, 8, 11, 22, 23, 24, 25, 34).

## How the brand system stays in sync with the main site

The canonical brand palette and typography come from `~/Studio/Websites/WildWooHooDotCom/wwh-brand-tokens.css`. This repo carries a **copy** at `css/wwh-brand-tokens.css`, identical at build-time, marked verbatim. If the main site updates the tokens, mirror the change here.

The shop-local `css/shop.css` is independent. It does not try to clone the main site's effects layer (showreel, voxel hero, splash lock). When the shop migrates to its e-commerce backend (Shopify per strategy doc), the theme will re-derive from `wwh-brand-tokens.css` again.

Fonts are loaded from Google Fonts: Syne, Inter, Instrument Serif, Libre Baskerville, Caveat. Same stack as the main site.

## Recommended phased launch (see STRATEGY-SUMMARY.md)

This scaffold is intentionally backend-agnostic. The recommended path:

- **Phase 1 (Q3 2026):** open with digital downloads, use **Lemon Squeezy** embedded buy buttons on this static scaffold. AU$0/mo fixed cost. Lemon Squeezy is the merchant-of-record so AU GST + EU VAT + US sales tax are handled for you.
- **Phase 2 (Q4 2026):** add POD merch via **Shopify Lite** (AU$9/mo) + Printful Australia. Embed Shopify Buy Buttons on this scaffold.
- **Phase 3 (2027, only when justified):** migrate to **Shopify Basic** (AU$45/mo) when SKUs > 15, or limited drops live, or revenue > AU$3K/mo.

The strategy doc's Shopify-first plan is the destination state, not the launch state. See `STRATEGY-SUMMARY.md` for the full reasoning.

## What's intentionally NOT here

| Not here | Why |
|---|---|
| Cart, checkout, payment | Phase 1 will use embedded Lemon Squeezy buy buttons. Phase 2 will use Shopify Lite Buy Buttons. Neither is wired yet. |
| Real product copy | Products do not exist yet. Placeholders only. |
| Analytics pixels | Get added when traffic is enough to read, not before. |
| Music releases | Live on Bandcamp (planned: welimusic.bandcamp.com). |
| Sync EPK | Lives on wildwoohoo.com/music-and-entertainment/. |
| Programme bookings | Live on drweli.com (cockpit / direct). |
| Newsletter signup | Defer until first 50 subscribers ask for it, then Buttondown. |
| Indigenous-art-inspired products | Out of scope without documented ICIP consultation. See main `~/Studio/CLAUDE.md`. |

## Discipline this repo inherits

From `~/Studio/CLAUDE.md` and `~/Studio/Websites/CLAUDE.md`:

- **Brand-domain rule.** WildWooHoo content lives on `wildwoohoo.com` (and now `shop.wildwoohoo.com`); Dr WELI content lives on `drweli.com`. Don't cross the streams.
- **AU English.** behaviour, programme, centre, organise, realise, colour.
- **Anti-AI-tell.** No em-dashes. No curly quotes. No Furthermore / Moreover / Additionally / In conclusion / Importantly / leverage / robust / delve / tapestry.
- **No overclaim.** No "show-stopping", "vanguard", "next big thing".
- **No re-introducing struck terms.** "Brain·Body·Planet" stays struck. "Living Wild" stays struck as a framing word.
- **Existing copy is good.** Lean on what the strategy docs already say. Don't rewrite.
- **No live-site changes** without WELI's explicit go. This repo is fine to evolve locally; pushing to the live shop subdomain requires the go-ahead.

## Reading list for future sessions

| Where | What |
|---|---|
| `STRATEGY-SUMMARY.md` (this repo) | Distilled shop strategy |
| `TODO.md` (this repo) | Next concrete steps |
| `~/Studio/Strategy-Hub-2026/01_WildWooHoo-Studio/SHOP-PRODUCTS-PIPELINE-PLAN.md` | The full 51KB shop strategy doc |
| `~/Studio/Industry-Knowledge/immersion/shop/insights.md` | 35 product-page conventions to apply |
| `~/Studio/Industry-Knowledge/immersion/shop/plan.md` | Shop immersion plan |
| `~/Studio/Industry-Knowledge/immersion/shop/practitioners.md` | Practitioners studied for the insights |
| `~/Studio/Websites/WildWooHooDotCom/brand-kit/README.md` | Brand kit v5 |
| `~/Studio/Websites/WildWooHooDotCom/wwh-brand-tokens.css` | Canonical palette tokens |
| `~/Studio/Strategy-Hub-2026/01_WildWooHoo-Studio/_LOCKED-DECISIONS-2026-06-04.md` | Locked decisions parent doc |
| `~/Code/wildwoohoo-shop/README.md` | The Shopify management-layer app (port 3025) |
| `~/Code/wildwoohoo-books-companion/README.md` | The companion PWA app |
