# Steve Tonneau's personal site

Jekyll site on the [al-folio](https://github.com/alshedivat/al-folio) v1.2 starter, published at https://stonneau.github.io (GitHub Pages, repo `stonneau/stonneau.github.io`).

## Where things live

- Pages: `_pages/` (home = `about.md`, contact, software, presentations, cv, publications, projects). Menu order is `nav_order` in each page.
- Projects: `_projects/*.md` (cards on the projects page).
- News: `_news/YYYY-MM-DD-slug.md`, shown on the home page.
- Publications: `_bibliography/papers.bib` only. Edited by hand (no automatic sync with Google Scholar). Local PDFs go in `assets/pdf/` and are referenced by file name in the `pdf` field; anything heavy (videos, pptx, large PDFs) is linked from `https://stevetonneau.fr/files/...` instead of being copied here.
- Venue badge colours: `_data/venues.yml`. Social links: `_data/socials.yml`. The e-mail address is in `_data/contact.yml` only (obfuscated on the contact page by `protect_email: true`); never add `email:` to `socials.yml`, the theme would print it in clear text on the home page and in the search palette.
- Robots background: `assets/img/hrp2hyq.png`, applied in `_sass/_custom.scss`.
- `_includes/youtube.liquid`: responsive YouTube embed.

## Local preview

`docker compose up` then open http://localhost:8080 (baseurl is empty). Deployment is by `.github/workflows/deploy.yml` on push to `main` (publishes the `gh-pages` branch).

## Rules

- Never write the e-mail address in clear text in pages; use `{% al_email_protect_link site.data.contact.email %}`.
- al-folio's layouts, includes and Sass are gem-owned; prefer configuration and content over local overrides, and keep overrides small and documented.
