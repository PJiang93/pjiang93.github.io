# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Peng Jiang's personal academic website (https://pjiang93.github.io), a personalized fork of the [academicpages](https://academicpages.github.io/) Jekyll template (itself derived from Minimal Mistakes). Deployed via GitHub Pages from the `master` branch. Most work in this repo is content editing (talks, publications, news, CV), not theme development.

## Commands

```bash
bundle install                            # install Ruby deps (github-pages gem)
bundle exec jekyll serve -l -H localhost  # serve at localhost:4000 with live reload
docker compose up                         # alternative: serve via Docker, same port
```

- `_config.yml` is NOT reloaded by `jekyll serve` — restart the server after changing it.
- There are no tests or linters.
- `npm run build:js` regenerates `assets/js/main.min.js` (uglify) — only needed if you edit files under `assets/js/`. Never edit `main.min.js` directly.

## Content architecture

IMPORTANT: the live Publications, Talks, and Teaching pages (`_pages/publications.html`, `talks.html`, `teaching.html`) are **hand-written HTML lists** — the Jekyll collection loops in them are commented out or removed. To add a publication, talk, or course to those pages, edit the HTML list directly, newest first, following the existing markup.

The `_talks/`, `_publications/`, `_teaching/` collections still exist and any `YYYY-MM-DD-slug.md` file placed there is published at `/<collection>/<filename>/` (e.g. `_talks/2025-12-05-siouxland-ieee-talk.md` holds a talk's full abstract page), but such pages are only reachable if linked manually.

Standalone pages are in `_pages/`:

- `about.md` — the homepage (`permalink: /`). The "Recent News" section is a list of HTML `<details>` blocks, newest first; follow the existing inline-styled markup when adding news. It also contains the Google Analytics tag.
- `cv.md`, `grants.html`, `astar-lab.html`, `publications.html`, `talks.html`, `teaching.html` — the pages linked from the header.

Header navigation order/visibility is controlled by `_data/navigation.yml`, not by the pages themselves.

Site-wide identity (author sidebar, SEO name/description, publication categories, collection defaults/layouts) is in `_config.yml`. Theme code is `_layouts/`, `_includes/`, `_sass/`; `_site/` is generated output — never edit it.
