# kendibah-web

The website for [Kendibah](https://kendibah.com): the marketing page, the FAQ, the privacy policy
and the terms of service. Static HTML with no build step.

## Hosting

- **kendibah.com** is served by Cloudflare Pages from `main`, output directory `/`, with no
  build command. Merging to `main` publishes the site.
- `https://kendibah.com/` is the App Store support and marketing URL, so the root page must
  always link to a contact address. `privacy.html` and `terms.html` are linked from the app
  (`LegalURLs` in `xoloUno/kendibah-app`) and from the App Store metadata. Don't rename or move
  them.
- The app's links change host only through `scripts/update-legal-urls.sh` in kendibah-app.

## Files

- `index.html`: the marketing page, with the App Store badge and a Support section (FAQ,
  Contact, Privacy, Terms)
- `faq.html`: what Kendibah can do on Roku and Samsung TVs, and the TV settings it needs
- `privacy.html`, `terms.html`: the legal pages
- `images/`: web copies of the approved App Store screenshots (the framed captures, trimmed and
  saved as WebP), the app icon rendered from `KendibahApp/AppIcon.icon` with Icon Composer's
  `ictool`, and `og.png` for link previews

The App Store badge loads from Apple's marketing tools
(`toolbox.marketingtools.apple.com`). The page advertises Roku and Samsung only; the other
brands appear in the FAQ and the footer's trademark line.

Don't add `apple-itunes-app` (Smart App Banner) or `theme-color` tags to the home page: with
them, swiping back to it in Safari on iPhone scrolled it to the top (tested 2026-11-16).
