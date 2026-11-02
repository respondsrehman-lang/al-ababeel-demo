# Al Ababeel — Afghan Restaurant, Dubai (Real Business)

A website for **Al Ababeel Afghan Restaurant**, a newly opened Afghan restaurant in Saih Shuaib 2, Dubai, UAE — established **August 2026**.

*Ababeel* (ابوابیل) is the flock of swallows of Afghan folklore: swallows dive into fire to put it out, and hide the misfortune of God's people behind their wings. The brand centers on this story — one wing, one sky, one kitchen.

## Pages

| Page | Contents |
|---|---|
| `index.html` | Home — animated splash screen, hero, four signature dishes (Kabuli Pulao, Shinwari Karahi, Mantu, Mix BBQ), our story, visit band |
| `menu.html` | Segmented interactive menu — the menu is served in meal-time segments (Segment 01: Breakfast, 18 nashta dishes · Segment 02: Karahi, 9 wok dishes — all with local stock photos) plus a big search bar living in the hero, a sticky segment rail, and upcoming-segment cards that keep `menu.html#bbq` / `#karahi` / `#rice` / `#classics` deep-links alive |
| `visit.html` | Visit us — Google Map embed, phone, WhatsApp, directions, dine-in / takeaway cards |

## Design

- **Tricolor night theme** — Afghan flag gradient (black / green / red) washed at 135° over a near-black base, with gold accents (`#d8b264`), green (`#1f7a4d`) and red (`#a82731`). Tri-line flag dividers separate sections.
- **Original logo** — a mihrab-arch gate crest with minbar, twin pennants, wheat wreath and swallows (`assets/logo.svg`, inlined as `<symbol id="crest">` on every page). No third-party brand assets.
- **Splash screen** — the crest unveils with a light pulse on first visit of the browser session (`sessionStorage`) while the wordmark, tricolor ribbon and two waving half-flags from the top corners animate through; then the site reveals. Skipped when `prefers-reduced-motion` is on, or on later visits in the same session.
- **Segmented menu** — Segment 01 (Breakfast, 18 real nashta dishes) and Segment 02 (Karahi, 9 dishes: shinwari, Lahori, house and white karahis) are fully built. Each dish has its own downloaded stock photo (`assets/food/`, sourced from Wikimedia Commons — credit map inside `menu.html`), rendered from a JS data table with staggered entrance. A big search bar sits in the hero (finds dishes across name/Dari/description across both segments and hides sections with no matches), and a sticky segment rail jumps between segments. Old category deep-links (`#bbq`, `#karahi`, `#rice`, `#classics`) resolve to the matching segment (live) or upcoming-segment card.

## Development / test URL hooks

Query parameters understood by the pages (inert for normal visitors):

- `?nosplash` — skip the splash screen immediately.
- `?splashhold` — freeze the splash screen at its fully-animated state (screenshots/debug).
- `&got=<sectionId>` — after load, scroll instantly to a page section (used with `nosplash`).
- `&flat` — force all scroll-reveal animations to their final state (layout debugging).

## Spotlight: pricing honesty

The restaurant is brand new. No dish on the menu page currently carries a real AED price: dishes show a dashed **AED —** chip with an explanatory phone call-to-action until the family finalises pricing, and the Rice & Pulao segment (whose pricing the family has confirmed) is displayed as an upcoming "PRICING" segment rather than a half-empty list.

## Content integrity

**All business details on the site — phone number, WhatsApp number, address (V2GV+4X8, Saih Shuaib 2, Dubai, UAE) and establishment date (August 2026) — are real, supplied by the owner.** The restaurant deliberately has **no social media accounts, no online ratings and no reviews**, and none are faked on the site. Menu prices other than the rice section are intentionally left as placeholders.

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
