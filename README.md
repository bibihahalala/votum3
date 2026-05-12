# VOTUM3

The website for VOTUM3 — a brand strategy studio for founder-led and heritage businesses.

**Live site:** _(to be added once deployed)_

## Structure

This is a single-page HTML website with no build step or framework. Everything lives in one file.

```
votum3/
├── index.html      ← the entire website
├── README.md       ← this file
└── DEPLOY.md       ← deployment guide
```

## Editing

The site is written in plain HTML, CSS, and a small amount of JavaScript for the contact form. To edit:

1. Open `index.html` in any text editor — VS Code is recommended, but TextEdit, Sublime, or even GitHub's web editor work.
2. Make your changes.
3. Save the file. If editing locally, commit and push to GitHub. If editing on GitHub.com, commit directly.
4. GitHub Pages rebuilds the site automatically within ~1 minute.

## Contact form

The form on the page submits to **Formspree** (https://formspree.io). Submissions are sent as email to **vivala@votum3.io**.

To change where submissions go, update the Formspree form settings — no code change needed.

To change which Formspree form is used, edit the `action` attribute on the `<form>` tag inside `index.html`.

## Brand colours

| Colour      | Hex       | Use                              |
|-------------|-----------|----------------------------------|
| Purple      | `#3C2153` | Primary brand, logo, accents     |
| Mint        | `#6F989C` | Secondary accent, the "3" mark   |
| Black       | `#1D1D1B` | Body text                        |
| Cream       | `#F2EFE8` | Background                       |
| Cream warm  | `#EAE6DC` | Card backgrounds, form, projects |

## Typography

The site uses **Lato** (loaded from Google Fonts) — the same font specified in the brand guidelines.

## Logo

The triquetra mark is embedded as inline SVG in the HTML for crisp rendering at any size. There is no separate logo file dependency.

## In Votum we trust.
