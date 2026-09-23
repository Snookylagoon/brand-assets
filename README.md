# brand-assets

Public hosting for company logo images, served over HTTPS by GitHub Pages so that
they can be referenced directly from HTML email signatures in Outlook and Gmail.

Email clients do not render SVG and will not display images from a private
repository, so every logo here is published as a **PNG** in a **public** repository.

**Live site:** https://snookylagoon.github.io/brand-assets/

## The golden rule

> **Never rename, move or delete a published logo. Every email already sent links to
> its exact address. To update a logo, replace the file under the same name.**

An email signature does not contain the picture itself — it contains a link to the
picture. Renaming or deleting a file breaks that link in every message already sitting
in someone else's inbox, and the logo turns into a broken-image placeholder.

## Folder structure

```
/
├── .nojekyll                 Tells GitHub Pages to serve files exactly as they are
├── index.html                Preview page: every logo, its URL and a copy button
├── README.md                 This file
└── logos/
    ├── kapiti-management/
    │   └── kapiti-management-logo.png
    ├── marcus-solomon/
    │   └── marcus-solomon-logo.png
    └── hexagon-holdings/
        └── hexagon-holdings-logo.png
```

One folder per company, named with the company slug. Every file inside a company
folder begins with that same slug, so a file is never ambiguous once downloaded.

## Naming convention

```
logos/<company-slug>/<company-slug>-<variant>.png
```

- **Lowercase only.** No capital letters.
- **Hyphens only.** No spaces, underscores or accented characters.
- **`.png` only.** Convert any SVG or JPG source to PNG before publishing.

| Company | Slug |
|---|---|
| Kapiti Management | `kapiti-management` |
| Marcus Solomon Management | `marcus-solomon` |
| Hexagon Holdings | `hexagon-holdings` |

Common variants:

| Variant | Meaning | Published width | Displayed width |
|---|---|---|---|
| `logo` | Full logo, for a light or white background | 400 px | 200 px |
| `logo-dark` | Full logo, for a dark background | 400 px | 200 px |
| `icon` | Icon or monogram only | 160 px | 80 px |

Images are published at **twice** their intended display width so that they stay sharp
on high-resolution (Retina) screens. Always set `width` and `height` in the email HTML
to the *display* size, not the published size.

## Resulting public URL

```
https://snookylagoon.github.io/brand-assets/logos/<company-slug>/<file-name>.png
```

## What belongs in this repository

This repository is **public**. Anyone on the internet can read every file in it.

- **Allowed:** logo PNG files, `index.html`, `README.md`, `.nojekyll`.
- **Not allowed:** anything else — no personal data, no documents, no spreadsheets,
  no contracts, no credentials, no API keys, no `.env` files, no draft artwork.

## Adding or updating a logo

See the preview page at https://snookylagoon.github.io/brand-assets/ for every current
logo and its exact URL. To add a new one, place the PNG in the correct company folder
using the naming convention above, then add a matching entry to the `LOGOS` list near
the top of `index.html`. To update an existing logo, overwrite the file, keeping the
name exactly as it is. Allow a minute or two for GitHub Pages to republish.
