# Al Ababeel — Afghan Restaurant, Dubai (Real Business)

A website for **Al Ababeel Afghan Restaurant**, a newly opened Afghan restaurant in Saih Shuaib 2, Dubai, UAE — established **August 2026**.

*Ababeel* (ابوابیل) is the flock of swallows of Afghan folklore: swallows dive into fire to put it out, and hide the misfortune of God's people behind their wings. The brand centers on this story — one wing, one sky, one kitchen.

## Pages

| Page | Contents |
|---|---|
| `index.html` | Home — animated splash screen, hero, four signature dishes (Kabuli Pulao, Shinwari Karahi, Mantu, Mix BBQ), our story, visit band |
| `menu.html` | Full interactive menu — 10 categories / ~68 dishes with sticky category tabs, live search, deep-links and dish photos |
| `visit.html` | Visit us — Google Map embed, phone, WhatsApp, directions, dine-in / takeaway cards |

## Design

- **Tricolor night theme** — Afghan flag gradient (black / green / red) washed at 135° over a near-black base, with gold accents (`#d8b264`), green (`#1f7a4d`) and red (`#a82731`). Tri-line flag dividers separate sections.
- **Original logo** — a mihrab-arch gate crest with minbar, twin pennants, wheat wreath and swallows (`assets/logo.svg`, inlined as `<symbol id="crest">` on every page). No third-party brand assets.
- **Splash screen** — the crest unveils with a light pulse on first visit of the browser session (`sessionStorage`) while the wordmark, tricolor ribbon and two waving half-flags from the top corners animate through; then the site reveals. Skipped when `prefers-reduced-motion` is on, or on later visits in the same session.
- **Interactive menu** — dishes are rendered from a JS data table; the sticky tab strip filters by category with per-category counts, a search box filters live, and `menu.html#rice` style deep-links jump to a category.

## Development / test URL hooks

Query parameters understood by the pages (inert for normal visitors):

- `?nosplash` — skip the splash screen immediately.
- `?splashhold` — freeze the splash screen at its fully-animated state (screenshots/debug).
- `&got=<sectionId>` — after load, scroll instantly to a page section (used with `nosplash`).
- `&flat` — force all scroll-reveal animations to their final state (layout debugging).

## Spotlight: pricing honesty

The restaurant is brand new. Only the **Rice & Pulao** section carries real AED prices (supplied by the family); every other dish shows a dashed **AED —** chip with an explanatory note bar and a phone call-to-action, until the family finalises the rest of the pricing.

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
