# DANES ScHack 2026 — Website

Static website for the **First DANES Summer School and Hackathon (DANES ScHack 2026)**,
University of Turin, Italy, July 6–10, 2026.

Published via **GitHub Pages** (main branch, root folder).

---

## Site structure

| File | Page | Edit when… |
|------|------|-----------|
| `index.html` | Home | Updating key facts, about text, or organiser info |
| `tracks.html` | Track descriptions | Editing track descriptions, hackathon focus, teacher lists |
| `program.html` | Full schedule | Adding/updating the daily schedule table |
| `teachers.html` | Teacher cards | Adding, updating, or replacing teacher info |
| `registration.html` | Registration form | Swapping the Google Form URL |
| `styles.css` | All styles | Changing colours, fonts, layout |
| `images/` | Logos, hero | Adding logos and hero background image |

---

## GitHub Pages setup

Configure GitHub Pages in **Settings → Pages**:
- **Source:** Deploy from a branch
- **Branch:** `main` / `(root)`

The `.nojekyll` file at the repo root prevents GitHub from running Jekyll processing on
the plain HTML files.

---

## Pending TODOs (operator actions required)

### 1. Hero image (`index.html`)
Replace the placeholder gradient in `.hero` (in `styles.css`) with a real image:
```css
/* In styles.css, update the .hero rule: */
background: linear-gradient(rgba(51,3,39,0.75), rgba(26,3,16,0.85)),
            url('images/hero-bg.jpg') center/cover no-repeat;
```
Save a high-quality CC-licensed image (e.g. Mole Antonelliana from Wikimedia Commons) as
`images/hero-bg.jpg`.

### 2. University of Turin logo (`index.html`)
Download the official logo from https://www.unito.it and save as `images/unito-logo.png`.
Used in the organisers row on the home page.

### 3. DANES logo
Download from https://opendanes.org or the OpenDANES GitHub repo and save as
`images/danes-logo.png`. Used as favicon and nav logo on all pages.

### 4. Full registration form (`registration.html`)
The page currently embeds the pre-registration form
(`1FAIpQLSfT83XqI2rfPPcjtQg0vT_YMG8f_1qjt3_ibGWsiQLeltbgEQ`).
Once the full registration form is live, replace the `src` attribute of the `<iframe>`
and the fallback `<a>` link with the new form URL (`/viewform?embedded=true` variant).
Look for the comment: `<!-- TODO: replace FORM_ID ... -->` in `registration.html`.

### 5. Track 2 schedule (`program.html`)
Replace the "Full schedule coming soon" placeholder cells in all five day-tables with
the actual Track 2 schedule once received from Morris Alper and Steffen Bauer
(expected by week of 6 April 2026). Look for: `<!-- TODO: replace placeholder with Track 2 schedule -->`.

### 6. Track 3 replacement teacher (`tracks.html`, `teachers.html`)
Replace `[Replacement TBD]` with the confirmed teacher's name, rank, affiliation, and
expertise once a replacement for Cristina Ichim is identified.
Look for: `<!-- TODO: replace [Replacement TBD] ... -->` in both files.

---

## Design system

Colours and typography are taken directly from the OpenDANES design system
([opendanes.org](https://opendanes.org), source:
[`_sass/_variables.scss`](https://github.com/DigitalPasts/openDANES/blob/main/_sass/_variables.scss)).

| Token | Value | Use |
|-------|-------|-----|
| `--primary` | `#52053E` | Nav, footer, headings |
| `--primary-dark` | `#330327` | Hover states |
| `--teal` | `#05878a` | Links, Track 1 accent |
| `--contrast` | `#feda75` | Nav hover, callouts |
| `--bg` | `#FEFBF1` | Page background |
| `--track1` | `#05878a` | Track 1 teal |
| `--track2` | `#c9543b` | Track 2 terracotta |
| `--track3` | `#9a6b23` | Track 3 warm brown |
| `--font-main` | `'Taviraj', serif` | All body &amp; heading text |

Layout is inspired by [AI4AS 2026](https://ai4asconference.github.io/2026/).

---

## Local preview

No build step required. Open any `.html` file directly in a browser, or use a simple
local server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

---

## Licence

Content: © 2026 DANES Network — [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/)
