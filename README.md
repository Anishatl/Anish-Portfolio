# anishatl.github.io/Anish-Portfolio

Personal portfolio. Plain static HTML, CSS and self-hosted fonts with no build
step and no dependencies. GitHub Pages serves it from the repo root.

## Pages

```
index.html                    Home: hero, highlights, featured projects
about.html                    Story, experience, education, skills
projects.html                 All projects (card grid with filters)
projects/*.html               One page per project (10)
research.html                 Beyond the Scan + other papers
research/beyond-the-scan.html Full research write-up
beyond.html                   Beyond Engineering: guitar, art, cricket, chess
resume.html                   Resume, viewable in the page + downloadable PDF
assets/anish-bhatia-resume.pdf  Hosted resume (no phone number or home address)
```

## Adding photos

Photo slots show a dashed "coming soon" frame until the file exists. To fill one,
drop an image with the exact name below into `assets/img/`. No code changes are needed.

| File                        | Where it shows                 |
|-----------------------------|--------------------------------|
| `assets/img/headshot.jpg`   | Home hero and About page       |
| `assets/img/music-guitar.jpg` | Beyond Engineering: Guitar   |
| `assets/img/cricket.jpg`    | Beyond Engineering: Cricket    |
| `assets/img/chess.jpg`      | Beyond Engineering: Chess      |

Square photos work best for the headshot (it's cropped to a circle). Keep files
under ~300 KB; export as JPG at ~1200px wide.

## Updating the resume

Replace `assets/anish-bhatia-resume.pdf` with a new PDF (strip the phone number
and home address first), and update the text version inside `resume.html` to match.

## Design

- Colors: navy `#0B1F3A`, Georgia Tech gold `#B3A369`, off-white `#FAFAF7`.
  Tokens live at the top of `assets/css/site.css`; dark mode follows the device.
- Type: Space Grotesk (headings) and Inter (body), self-hosted in `assets/fonts/`.
- Layout: one centered column; the nav collapses to a Menu button under 820px.

## Local preview

```sh
python3 -m http.server 8000
```

Then open <http://localhost:8000>.
