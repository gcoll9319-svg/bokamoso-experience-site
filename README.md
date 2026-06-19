# Bokamoso Experience NPC — Website

A fast, mobile-first, single-page site for Bokamoso Experience NPC (go-kart sessions, school
outreach days, and group bookings in Kagiso, Krugersdorp). Built as plain HTML/CSS/JS — no
build step, no framework, no dependencies — so it loads quickly on mobile data and can be
deployed anywhere.

## Structure

```
index.html          All page content and sections
css/styles.css       All styling (colors, layout, responsive breakpoints)
js/main.js           Mobile nav toggle, gallery lightbox, footer year
images/              Icons and placeholder illustrations (see below)
```

## Previewing locally

No build tools needed. Either:

- Open `index.html` directly in a browser, or
- Run a tiny local server from this folder, e.g. `python3 -m http.server 8000`, then visit
  `http://localhost:8000`.

## Before going live — things to finish

1. **Real photos.** The hero graphic and the 6 gallery tiles in `images/` are placeholder
   illustrations (clearly labelled "Photo coming soon"). Replace them with real photos of the
   go-karts, kids, and events:
   - Drop new images into `images/` (JPG, compressed/optimized for web, ideally under ~200KB
     each).
   - Update the `src` (and `data-full` on gallery buttons) in `index.html` to point to the new
     filenames.
   - For the gallery, a 4:3 aspect ratio matches the existing grid best.
2. **Facebook link.** The footer Facebook link is a placeholder (`href="https://www.facebook.com/"`)
   marked with a `<!-- TODO -->` comment in `index.html`. Replace it with the real Bokamoso
   Experience Facebook page URL.
3. **Opening hours.** The Visit section currently shows "Closed Monday–Friday, Saturday opens
   11am" with a note to confirm — double-check this is accurate and update `index.html` if
   hours change.
4. **Social share image.** `og:image` currently points to the SVG hero illustration. Most chat
   apps (WhatsApp, Facebook) render link previews more reliably with a real JPG/PNG. Once you
   have a good photo, save it (e.g. `images/social-share.jpg`, ~1200×630px) and update the
   `og:image` / `twitter:image` meta tags in `index.html`. Also update `og:image` to a full
   `https://...` URL once the site has a live domain (relative paths can fail in some link
   preview crawlers).

## Editing content

All text lives directly in `index.html` — there's no CMS. Search for the section heading
(e.g. `id="about"`, `id="offer"`, `id="visit"`) and edit the text in place.

The primary call-to-action everywhere is the WhatsApp button, linking to
`https://wa.me/27718281632`. If the WhatsApp number ever changes, update it in all four
places it appears in `index.html` (nav, hero, visit section, footer) plus the `tel:` links
and the phone number text.

## Deploying

Any static host works since there's no server-side code or build step:

- **Netlify / Vercel:** drag-and-drop the project folder in their dashboard, or connect this
  Git repo for automatic deploys on push.
- **GitHub Pages:** enable Pages on this repo (Settings → Pages → deploy from branch), serving
  from the root of the main branch.

## Notes

- Fonts use the device's default system font stack (no Google Fonts) to avoid extra network
  requests on mobile data.
- Icons are inline SVG (WhatsApp, offer cards) — no icon library or extra requests.
- The map embed and "Get Directions" link use Google's address-based query (no API key
  required); update the address string in `index.html` if it ever changes.
