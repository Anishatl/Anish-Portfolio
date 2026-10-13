# anishatl.github.io/Anish-Portfolio

Personal portfolio. Plain static HTML, CSS and self-hosted fonts — no build
step, no dependencies. Served by GitHub Pages from the repo root.

## Structure

```
index.html              single-page site: work, experience, research,
                        skills, education, contact, drawing
projects/*.html         one page per project (12)
assets/css/site.css     the whole design system
assets/fonts/           IBM Plex Sans + Mono, latin subset, woff2
assets/img/             WebP imagery + og-preview.jpg
```

## Design system

"Lab notebook / instrument." Structure comes from an engineer's computation
pad — ruled background, a brick-red margin rule, binder index tabs on the
outer edge, figure-numbered plates. Emphasis comes from instrumentation:
measured values are set apart as *readings* rather than typed inline.

Tokens live at the top of `site.css`:

| Token     | Value     | Use                                      |
|-----------|-----------|------------------------------------------|
| `--paper` | `#EFF2EB` | page background                          |
| `--grid`  | `#DCE3D6` | ruling                                   |
| `--ink`   | `#16201C` | body text                                |
| `--brick` | `#A63A2B` | margin rule, section marks — structural  |
| `--olive` | `#4F5A50` | metadata, captions                       |
| `--blue`  | `#1F4260` | links and measured values                |

`--unit` (26px) is the grid pitch; vertical spacing is multiples of it, so the
ruling is visibly the layout guide rather than decoration.

Conventions worth keeping if you edit:

- Mono type is applied *systematically* — every date, reading and caption. It
  is the concept's voice. Half-applied is worse than not at all.
- One motion moment only: the tick on the active index tab.
- No rounded corners, no drop shadows, no skill bars or proficiency ratings.
- Meta is set as small spec tables, not middle-dot strings.

## Adding a headshot

Drop a square image at `assets/img/headshot.webp` (600×600 or larger), then add
this inside `<header class="masthead">` in `index.html`:

```html
<img src="assets/img/headshot.webp" alt="Anish Bhatia" width="600" height="600"
     style="width:120px;border:1px solid var(--ink);margin-bottom:14px">
```

## Adding the resume

Put a PDF at `assets/anish-bhatia-resume.pdf` and link it from the contact
list. **Strip the home address and phone number from the hosted copy first** —
they are fine on a resume sent directly to a recruiter, not on an indexed page.

## Local preview

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Checks worth re-running after edits

- No horizontal scroll at 390px wide.
- Body text stays at or above 4.5:1 contrast on `--paper`.
- Every `<img>` has real alt text describing the engineering content, not
  "robot photo".
