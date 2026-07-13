# ClicksAndBits Apps — Website

The marketing + compliance website for **ClicksAndBits Apps**, the app studio of
**JEH Electronics**. Plain static HTML/CSS/JS — no build step, hosts anywhere
(GitHub Pages, Netlify, Cloudflare Pages, any static host).

## Structure

```
/
├── index.html            Home
├── apps.html             App catalog
├── about.html            About JEH Electronics
├── brand.html            Brand guidelines (colors, logo, type)
├── privacy.html          Master privacy policy (Play/App Store compliant)
├── terms.html            Terms of use
├── support.html          Help & FAQ
├── contact.html          Contact + company info
├── 404.html              Not-found page
├── apps/
│   └── example-app.html  Per-app template (copy this for each new app)
└── assets/
    ├── css/styles.css    Design system — all colors/components live here
    ├── js/main.js        Mobile nav, active link, footer year
    └── img/
        ├── icon.svg      Logo mark (nav, favicon, hero)
        ├── logo-full.svg Full logo with wordmark
        └── logo-full.jpg Raster fallback of the full logo
```

## Adding a new app

1. **Copy the template:** duplicate `apps/example-app.html` to
   `apps/your-app-name.html`.
2. **Edit the page:** update the `<title>`, meta description, app name, icon
   emoji/image, tags, features, the **Data Safety** table, the **permissions**
   table, and the cloud-sync / data-deletion text to match the real app.
3. **Add store links:** replace the two `href="#"` store badges with your real
   Google Play and App Store URLs (remove one if the app isn't on that platform).
4. **List it:** add a matching `<article class="card app-card">…</article>` to
   the grids in `apps.html` (and optionally `index.html`), pointing to the new
   page.
5. **App-store privacy URL:** the URL of the per-app page
   (e.g. `https://clicksandbitsapps.com/apps/your-app-name.html`) is what you
   paste into the **Google Play Console** and **App Store Connect** as that app's
   privacy policy link. Apps that collect nothing can instead point at
   `privacy.html`.

## Compliance notes

- `privacy.html` is the **master policy**; each per-app page adds the specific
  data/permissions disclosures Google Play and Apple require. Per-app pages
  state that they control over the master policy for that app.
- Update the **"Last updated"** dates whenever you change policy text.
- Confirm the contact emails resolve before launch:
  `support@clicksandbitsapps.com` and `privacy@clicksandbitsapps.com`.

## Brand quick reference

| Role            | Color            | Hex       |
|-----------------|------------------|-----------|
| Primary         | Sky Blue         | `#00ADEE` |
| Primary         | Deep Indigo      | `#2E3191` |
| Dark            | Near Navy        | `#2E3159` |
| Secondary       | Slate Blue       | `#5C8DD3` |
| Accent "bit"    | Clicks Green     | `#36BE4A` |
| Accent "bit"    | Light Green      | `#70E657` |
| Accent "bit"    | Bit Yellow       | `#F4CB19` |
| Accent "bit"    | Bit Orange       | `#F4A419` |

Full guidelines live at `brand.html`. Fonts: **Poppins** (display) + **Nunito
Sans** (body), loaded from Google Fonts.

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```
