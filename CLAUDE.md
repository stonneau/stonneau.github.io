# Steve Tonneau's personal site

Jekyll site on the [al-folio](https://github.com/alshedivat/al-folio) v1.2 starter, published at https://stonneau.github.io (GitHub Pages, repo `stonneau/stonneau.github.io`).

## Where things live

- Pages: `_pages/` (home = `about.md`, contact, software, presentations, grants, cv, publications, projects). Menu order is `nav_order` in each page.
- Projects: `_projects/*.md` (cards on the projects page).
- News: `_news/YYYY-MM-DD-slug.md`, shown on the home page.
- Publications: `_bibliography/papers.bib` only. Edited by hand (no automatic sync with Google Scholar). Give each entry a `video` (YouTube link when one exists) and, for a paper covered by a project page, a `website` field. The type filter on the publications page reads the BibTeX entry type (`@article` = journal, `@inproceedings`/`@incollection` = conference, arXiv preprints and editorials = other). Local PDFs go in `assets/pdf/` and are referenced by file name in the `pdf` field; anything heavy (videos, pptx, large PDFs) is linked from `https://stevetonneau.fr/files/...` instead of being copied here.
- Venue badge colours: `_data/venues.yml`. Social links: `_data/socials.yml`. The e-mail address is in `_data/contact.yml` only (obfuscated on the contact page by `protect_email: true`); never add `email:` to `socials.yml`, the theme would print it in clear text on the home page and in the search palette.
- Robots background: `assets/img/hrp2hyq.png`, applied in `_sass/_custom.scss`.
- `_includes/youtube.liquid`: responsive YouTube embed.
- `_pages/supervision.md`: CDT-D2AIR application info and the lists of current and past students and post-docs. **To update every year**: the intake, the deadline and the decision dates (copy them from https://www.cdt-d2air.uk/apply), and the student lists. The name links go to `/publications/#<lowercase name>`: the theme's publication filter only matches lowercase hashes. The same CDT deadline is repeated in `_news/2026-10-07-cdt-d2air-recruiting.md`.

## Capitals

Every page title and heading starts with a capital letter (the theme writes them in lowercase: `_sass/_custom.scss` and the front matter `title:` fix that). Titles and headings use sentence case: capital only on the first word and on names and acronyms (`MPC`, `Talos`, `L1-norm`). A word after a colon starts in lowercase, unless it is a name (`MEMMO: Memory of Motion`). Paper titles follow the same rule everywhere, in `papers.bib` and in the pages that quote them; protect acronyms and names with braces in the BibTeX title (`residual {MPC}`).

## Local preview

`docker compose up` then open http://localhost:8080 (baseurl is empty). Deployment is by `.github/workflows/deploy.yml` on push to `main` (publishes the `gh-pages` branch).

## Rules

- Never write the e-mail address in clear text in pages; use `{% al_email_protect_link site.data.contact.email %}`.
- al-folio's layouts, includes and Sass are gem-owned; prefer configuration and content over local overrides, and keep overrides small and documented.
