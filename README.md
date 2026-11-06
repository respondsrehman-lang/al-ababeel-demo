# Al Ababeel — Afghan Restaurant, Dubai (Real Business)

A website for **Al Ababeel Afghan Restaurant**, a newly opened Afghan restaurant in Jessy Shun Tong Saloon, Harmony point Shop 06 Saih Shuaib 2 - Dubai Industrial city - Dubai U.A.E — established **August 2026**.

*Ababeel* (ابوابیل) is the flock of swallows of Afghan folklore: swallows dive into fire to put it out, and hide the misfortune of God's people behind their wings. The brand centers on this story — one wing, one sky, one kitchen.

## Pages

| Page | Contents |
|---|---|
| `index.html` | Home — animated splash screen, hero, three signature dishes (Kabuli Pulao, Mutton Shinwari Karahi, Mix BBQ), our story, visit band |
| `menu.html` | Segmented interactive menu — the menu is served in meal-time segments (Segment 01: Breakfast, 18 nashta dishes · Segment 02: Karahi, 9 wok dishes · Segment 03: Handis, 5 clay-pot dishes · Segment 04: Veg, 11 daal & sabzi dishes · Segment 05: BBQ & Charcoal, 10 grill dishes · Segment 06: Rice, 7 biryani & pulao dishes — with local stock photos; Lahori Chaney intentionally appears in both Breakfast and Veg) plus a big search bar living in the hero and a sticky segment rail (`#bbq` / `#rice` deep-links load the live Segments 05 / 06) |
| `visit.html` | Visit us — Google Map embed, phone, WhatsApp, directions, dine-in / takeaway cards |
| `legal.html` | Terms of Use & Privacy Policy — original-design ©/™ ownership claim (permission required to reuse design/menu), price-placeholder & stock-photo honesty, zero-collection privacy statement (only the sessionStorage splash flag; tel/WhatsApp go direct to the owner's number; the Google map loads under Google's own terms), consent-first clause for any future analytics under UAE PDPL |

## Design

- **Tricolor night theme** — Afghan flag gradient (black / green / red) washed at 135° over a near-black base, with gold accents (`#d8b264`), green (`#1f7a4d`) and red (`#a82731`). Tri-line flag dividers separate sections.
- **Original logo** — a mihrab-arch gate crest with minbar, twin pennants, wheat wreath and swallows (`assets/logo.svg`, inlined as `<symbol id="crest">` on every page). No third-party brand assets.
- **Splash screen** — the crest unveils with a light pulse on first visit of the browser session (`sessionStorage`) while the wordmark, tricolor ribbon and two waving half-flags from the top corners animate through; then the site reveals. Skipped when `prefers-reduced-motion` is on, or on later visits in the same session.
- **Segmented menu** — Segment 01 (Breakfast, 18 real nashta dishes), Segment 02 (Karahi, 9 dishes: shinwari, Lahori, house and white karahis), Segment 03 (Handis, 5 dishes: brain masala, chicken, white, jalfrezi and Kashmiri handis), Segment 04 (Veg, 11 dishes: daal tadka, mash fry, mix vegetable, chana fry, anda tikki, Lahori chaney, palak paneer, bhindi, anda chaney, daal gosht and palak gosht with a chicken/mutton choice), Segment 05 (BBQ & Charcoal, 10 dishes: special BBQ mutton seekh kebab, chicken seekh kebab, chicken malai boti, chicken tikka boti, mutton tikka boti, charsi tikka, afghani tikka, pepper / green-chilli / house chicken charcoal) and Segment 06 (Rice, 7 dishes: chicken biryani, kabuli pulao, fish biryani, seekh kabab biryani, reshmi kabab biryani, special mix grill biryani and chicken tikka biryani) are fully built. Each dish has its own downloaded stock photo (`assets/food/`, sourced from Wikimedia Commons + Unsplash — credit map inside `menu.html`), rendered from a JS data table with staggered entrance. A big search bar sits in the hero (finds dishes across name/Dari/description across all segments and hides sections with no matches), and a sticky segment rail jumps between segments — only the chosen pill glows gold while the unchosen ones stay dark with a continuous white light riding their borders. Old category deep-links (`#bbq`, `#karahi`, `#handis`, `#veg`, `#rice`) resolve to the matching live segment.

## Development / test URL hooks

Query parameters understood by the pages (inert for normal visitors):

- `?nosplash` — skip the splash screen immediately.
- `?splashhold` — freeze the splash screen at its fully-animated state (screenshots/debug).
- `&got=<sectionId>` — after load, scroll instantly to a page section (used with `nosplash`).
- `&flat` — force all scroll-reveal animations to their final state (layout debugging).

## Spotlight: pricing honesty

The restaurant is brand new. No dish on the menu page currently carries a real AED price: dishes — on every segment, including the new Rice & Pulao Segment 06 — show a dashed **AED —** chip with an explanatory phone call-to-action until the family finalises pricing.

## Content integrity

**All business details on the site — phone number, WhatsApp number, address (V2GV+4X8 · Jessy Shun Tong Saloon, Harmony point Shop 06 Saih Shuaib 2 - Dubai Industrial city - Dubai U.A.E) and establishment date (August 2026) — are real, supplied by the owner.** The restaurant deliberately has **no social media accounts, no online ratings and no reviews**, and none are faked on the site. Menu prices are intentionally left as placeholders on every segment — including the rice section — until the family finalises them.

## Stack

Three self-contained HTML pages — each page carries its own inline CSS/JS, no build step, no dependencies. Fonts: Cinzel (display), Jost (body), Amiri (Dari/Arabic) from Google Fonts. Vanilla JS (splash, scroll reveal, category tabs, search, mobile nav). Reduced-motion aware and keyboard-accessible. `Restaurant` JSON-LD schema on the home page.

## Deploy (GitHub Pages)

```bash
git init
git add .
git commit -m "Al Ababeel restaurant site"
git remote add origin https://github.com/<user>/al-ababeel-demo.git
git push -u origin main
```

Pages is served from the repo `Settings → Pages` (branch: `main`, root).
