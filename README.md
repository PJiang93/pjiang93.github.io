# pjiang93.github.io

Personal academic website of **Peng Jiang** — Assistant Professor of Cybersecurity, School of Interdisciplinary Informatics (Si2), University of Nebraska at Omaha.

Live site: **https://pjiang93.github.io**

Built with [Jekyll](https://jekyllrb.com/) on a customized fork of the [Academic Pages](https://github.com/academicpages/academicpages.github.io) template, deployed automatically by GitHub Pages from the `master` branch.

## Running locally

Requires Ruby with Bundler (`gem install bundler`).

```bash
bundle install
bundle exec jekyll serve -l -H localhost
```

Then open http://localhost:4000. Pages rebuild and reload automatically on change, **except** `_config.yml`, which requires a server restart.

Alternatively, with Docker:

```bash
docker compose up
```

## Editing content

| What | Where |
|------|-------|
| Homepage bio & news | `_pages/about.md` (news items are `<details>` blocks, newest first) |
| Publications | `_pages/publications.html` (hand-written HTML list) |
| Talks | `_pages/talks.html` (hand-written list); full abstracts can go in `_talks/YYYY-MM-DD-slug.md` |
| Teaching | `_pages/teaching.html` (hand-written list) |
| Grants | `_pages/grants.html` |
| ASTAR Lab | `_pages/astar-lab.html` |
| CV | `_pages/cv.md` |
| Header menu | `_data/navigation.yml` |
| Sidebar profile, SEO name/description | `_config.yml` |

PDFs and other downloadable files go in `files/`; images in `images/`.
