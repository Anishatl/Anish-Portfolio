# Build notes

Rebuild of the portfolio against the v4 brief. Design direction is "lab notebook /
instrument": faint full-page grid, a brick-red margin rule, index tabs on the far
left, figure-numbered photography, and measured values set in red-ruled reading
boxes.

## Structure

```
index.html                          Work / About / Experience / Research / Contact
projects/blitz.html                 flagship case study
projects/scouting.html
projects/cricket-analyzer.html
projects/water-purification.html
assets/css/site.css                 the whole design system
assets/fonts/*.woff2                IBM Plex Sans 400/600/700, Mono 400/500 (latin)
assets/img/*.jpg
```

The old `index.html` was 458 KB, almost all of it inline base64. It is now 17 KB.
Every image that was embedded in the old pages has been decoded, resized, optimised
and written to `assets/img/` as a real file.

## Open items

### [ASK ANISH] — flagged on the pages themselves

1. **Beyond the Scan artifact.** Is there a paper, poster, or repo? A linkable
   artifact would substantially strengthen the Research section. Flagged on
   `index.html#research`.
2. **Blitz electrical narrative.** The CAN bus routing section on
   `projects/blitz.html` reconstructs the reasoning behind the layout from the CAD
   render itself — the old repo had one sentence of electrical copy. Confirm or
   correct it before the site goes public, and add the specifics a reviewer will
   ask about: device count on the bus, wire gauges, and whether the turret run is a
   continuous service loop or a connectorised break.
3. **Dayul Lee.** Credited under his legal name on the water purification page. If
   he goes by David publicly, credit him the way he prefers.
4. **Résumé PDF.** Not in the repo, so nothing is linked yet. Drop the file in as
   `assets/anish-bhatia-resume.pdf` — **with the street address removed** — and add
   the link to the masthead and the Contact section.
5. **"What I would change" passages.** Every case study ends with one, because the
   brief asks to keep them. They are drafted, not transcribed — read them as
   proposed wording and correct anything that is not your actual view.

### Missing assets

These are named in the brief but were not in the repo, and they are too large to
move through the Google Drive connector in a coding session. Drop them into
`assets/img/` and they can be wired in:

- `IMG_2248.jpeg` — workshop assembly shot. Belongs in Blitz →
  "Manufacturing and assembly".
- Cricket analyzer: the 76-second demo and 16 screen recordings (Drive folder
  "Bowling App"). A short muted MP4 loop of the pose tracker belongs at the top of
  that page. Convert MOV → MP4, HEIC → WebP.
- Water purification: 16 photos + 3 videos of the build and test runs.

### Retired

These project pages carried the old design and are not in the v4 brief's five
projects. They were removed in this rebuild and remain in git history:
`ball-launcher`, `battery-crimp`, `beyblade`, `lithophane`, `road-case`. The
`scouting-software.html` page was replaced by `scouting.html`. The Art section was
dropped. Any of them can be brought back in the new design on request — the battery
crimp resistance testing in particular is measurement-discipline work that suits
this audience.

### Georgia Tech dates

The résumé gives `Aug 2024 – present` with an expected graduation of May 2028,
alongside separate UNG dual enrollment for `Aug 2024 – May 2026`. The site prints
the résumé's dates verbatim. If the Aug 2024 start refers to dual-enrollment
coursework at Georgia Tech rather than matriculation, it is worth saying so on the
page — a recruiter reading "Aug 2024 – present" and "first-year" together will
notice.

## Corrections applied from the brief

- Major is Computer Engineering (not Computer Science).
- Employer spelled **Chesstronics**.
- FRC tenure Aug 2022 – May 2026.
- 80+ scouts trained (not 40+).
- Cricket: injury rehab 2024–2025, currently in the Georgia Tech Cricket Club. The
  old "ultimately stepping back from the sport" line is gone.
- All high-school-admissions framing removed: weighted GPA, SAT, AP course lists,
  "Class of 2026", pathway completion.
- Water purification cost is **$2.41, over ten times cheaper than a typical water
  filter**. The retired "15× cheaper" figure appears nowhere.
- **Privacy:** the home street address and phone number are not on the site. Contact
  is email, LinkedIn and GitHub only.

## Deploying

Static, no build step. GitHub Pages: Settings → Pages → deploy from branch, root.
`.nojekyll` is present.

The canonical, Open Graph and sitemap URLs are all set to
`https://anishatl.github.io/Anish-Portfolio/`. **On a custom domain, search and
replace that base URL** across `index.html`, `projects/*.html`, `sitemap.xml` and
`robots.txt`.

## Accessibility and performance

Verified in Chromium at 1440px and 390px: no horizontal overflow on any page,
visible 2px focus outline on the index tabs, skip-to-content link first in tab
order, no heading-level skips, `prefers-reduced-motion` drops the tab tick
transition to 0s. Body text is #16201C on #F1F3EE (about 15:1); the olive
secondary text is about 5.4:1 and the stamped blue about 8:1, both above 4.5:1.

Fonts are self-hosted latin subsets with `font-display: swap`, the two used above
the fold are preloaded, every image carries `width`/`height`, and everything below
the fold is `loading="lazy"`.
