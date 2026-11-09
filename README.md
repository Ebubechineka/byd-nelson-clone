# BYD Nelson — Demo Sale Site Clone

A static, self-contained mirror of the **BYD Nelson Demo Sale** page and its supporting
site (Car Company Nelson / BYD New Zealand). Every page, stylesheet, script, image and
font is served from this repository — there are **no external dependencies and no
redirects** to the original site or any third party.

## Entry point

| | |
|---|---|
| **Main page** | [`byd-nelson_v2/byd-nelson-demo-sale/index.html`](byd-nelson_v2/byd-nelson-demo-sale/index.html) |
| **Site home** | [`byd-nelson_v2/index.html`](byd-nelson_v2/index.html) |
| **Pages** | 79 HTML files |
| **Files** | 1,684 |
| **Size** | ~260 MB |

## Structure

```
byd-nelson_v2/                     # pages (mirrors the original /webpages/byd-nelson_v2/)
├── byd-nelson-demo-sale/          # the demo-sale landing page
├── index.html                     # site home
├── latest-news/                   # news index
├── vehicle-details/
│   ├── vehicle/                   # individual vehicle detail pages
│   │   ├── 2026-BYD-Shark6/
│   │   ├── 2026-BYD-Sealion6/
│   │   ├── 2026-BYD-Sealion8/
│   │   └── 2026-BYD-Atto2/
│   ├── bundles/                   # site CSS + JS (sitestyles, foundation, photoswipe…)
│   ├── buyerscore/style/          # review-widget CSS + bs-icons webfont
│   ├── userfiles/styles/          # icons-custom webfont + styles
│   ├── Motorcentral/VehicleData/  # vehicle photography
│   ├── Userfiles/Image/           # logos and icons
│   └── extimg/                    # partner logos
├── p-*.html                       # individual content pages
└── <slug>/index.html              # news articles and model pages

byd-nelson/                        # shared assets (mirrors /webpages/byd-nelson/)
└── wp-content/uploads/            # WordPress media library
```

All internal links are **relative**, so the site works unchanged from a
GitHub Pages project subpath (`https://<user>.github.io/<repo>/`).

## Features

- Full site navigation, including the mobile hamburger menu
- Vehicle detail pages with photo galleries and specification tables
- News article pages
- Contact and finance enquiry forms (client-side rendering and validation)
- All original styling, fonts and imagery preserved

## Running locally

Any static file server works. From the repository root:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000/byd-nelson_v2/byd-nelson-demo-sale/index.html>.

> Opening the HTML files directly via `file://` will not work correctly — the pages
> rely on relative paths that need an HTTP origin.

## Deploying

Pushing to `main` triggers the included GitHub Actions workflow
([`.github/workflows/pages.yml`](.github/workflows/pages.yml)), which publishes the
repository to GitHub Pages. The site is then available at:

```
https://<user>.github.io/<repo>/byd-nelson_v2/byd-nelson-demo-sale/index.html
```

## Notes

- This is a **static archive**. Forms that originally posted to a server-side endpoint
  render and validate as normal but cannot submit — there is no backend.
- Analytics and tracking scripts from the original site are not active here.
- Content, text, images, structure and styling are reproduced as-is; nothing has been
  redesigned or rewritten.
