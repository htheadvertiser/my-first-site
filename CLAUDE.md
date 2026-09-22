# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A two-page static HTML personal/professional website for Hasan Alomari (digital ads specialist). There is no build system, package manager, framework, or test suite. Each page is one self-contained HTML file with inline CSS.

## Location

The site lives in `My Website Test/`, not the repo root:

- `My Website Test/index.html` is the home page (hero, about, skills, experience summary, testimonials, credentials).
- `My Website Test/projects.html` is the projects page: seven detailed project write-ups with metrics. It links back to `index.html`; every page links to it from the nav bar. The former "Work" case-study cards on `index.html` were removed because they duplicated the first three projects here.
- `My Website Test/experience.html` is the full work-history page (timeline plus education/certification). `index.html` keeps a summary timeline and links to it from the nav bar and a "Full experience" button. Like `about.html` and `skills.html`, it carries its own copy of the shared nav/footer/menu script. Note that the site is now more than two pages, and the nav links in all pages must be kept in sync when adding another.
- `My Website Test/testimonials.html` is the full testimonials page (the five client reviews with project title, dates, and strengths, taken from the Upwork profile). `index.html` keeps its testimonials section and links to it from the nav bar and an "All testimonials" button. The review wording must match `index.html`.
- `My Website Test/BlurredBG.png` is the profile photo, referenced by `index.html` via a relative path (`src="BlurredBG.png"`). It must stay in the same folder as `index.html`, or the image breaks.
- `My Website Test/Project details.txt` is the author's raw text for the seven projects on `projects.html`. Source material only, not part of the published site.
- `My Website Test/Hasan A. - Digital Ads Specialist ... - Upwork Freelancer from Ankara, Turkey.html` (+ its `..._files/` asset folder) is a saved copy of the author's Upwork profile page, kept only as reference source material for the copy on `index.html`. It is not part of the published site and should not be linked from either page.

## Working with the pages

- Plain HTML/CSS with no dependencies. Edit directly with Edit/Write.
- There is no shared stylesheet: `projects.html` carries its own copy of the design tokens (`:root` colors), nav, and footer styles from `index.html`. A change to the shared look (colors, fonts, nav, footer) must be made in both files. That includes the mobile hamburger menu (`.nav-toggle` button, its CSS, and the small inline script at the bottom of each page).
- To preview, open a file directly in a browser (`file://` works) or serve the `My Website Test/` folder with any static file server. Keep all files in that one folder, since the pages link to each other and to the photo by relative path.
- Fonts are pulled from Google Fonts (Inter, Fraunces) via a `<link>` tag. The pages need internet access for those to load and fall back to system fonts otherwise.
- Copy on `index.html` (bio, employment history, skills, testimonials, credentials) was sourced from the Upwork profile HTML. Copy on `projects.html` comes from `Project details.txt`. Neither syncs automatically.
