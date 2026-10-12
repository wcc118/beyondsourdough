# Beyond Sourdough website: repository guide

Public front end for Beyond Sourdough, a home micro-bakery in Marietta, Georgia. Static site, no build step, served by GitHub Pages at beyondsourdough.com (CNAME).

The business back office (plan, research, records, original photos) lives in the **private** repo `wcc118/beyond-sourdough-business`. Nothing from that repo is published here except web-ready images prepared for this site.

## Current stage

Coming-soon page (October 2026). The original blog site is archived in the private repo at `archive/website-v1/`. This repo's history was restarted on 2026-10-11.

## Structure

```
index.html        Coming-soon page (waitlist + Instagram)
404.html          Not-found page (old recipe URLs land here)
assets/img/       Web-ready images only
favicon.svg, favicon-32.png, favicon.ico, apple-touch-icon.png   Tab and home-screen icons (scored loaf on raisin)
CNAME             beyondsourdough.com
robots.txt
sitemap.xml       List every public page
```

Planned pages use folder URLs: `/bread/`, `/raisin-yeast-water/`, `/learn/<slug>/`, `/about/`, each an `index.html`.

## Rules

- **No personal identity.** Brand voice ("Beyond Sourdough"), no owner name, face, bio, or home address. Show a service area (Marietta, Georgia), never a street address.
- **No health or disease claims.** Nothing about diabetes, blood sugar, curing, or treating anything. This is a food seller's site; keep to flavor, process, and technique.
- **Images:** only web copies with all metadata stripped (phone photos contain GPS). Originals stay in the private repo's `photos/`. Check every image for faces, house exterior, windows/yard, mail, plates.
- **Waitlist form** on `index.html` posts to a Google Apps Script web app (owned by the business Gmail account) that writes to a Google Sheet and sends a confirmation email. The script source is in the private repo at `demand-test/waitlist-apps-script.gs`. The endpoint URL is public by design; the script validates input and ignores bot submissions. Keep the form short, collect only what the form already asks for, and never publish the Sheet or the list.
- Google Analytics `G-PZWCERQEYQ` on every page.
- Every page: title, meta description, canonical URL, Open Graph tags; schema.org JSON-LD where it fits (no address).
- CSS is inline in each page for now; move to a shared `assets/` stylesheet once there are several pages.
- Design tokens: raisin `#3b2330`, rye `#5a3a44`, crust `#c2843f`, flour `#f3ede4`, crumb `#d9bf9c`; Young Serif (headings) and Hanken Grotesk (body).

## Deploy

Commit to `main` and push; GitHub Pages deploys automatically.
