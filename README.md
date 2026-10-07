# stonneau.github.io

Personal page of Steve Tonneau (University of Edinburgh), built with [al-folio](https://github.com/alshedivat/al-folio) v1.2 (Jekyll) and published on GitHub Pages.

- Content: `_pages/`, `_projects/`, `_news/`, `_bibliography/papers.bib` (publications, edited by hand).
- Local preview: `docker compose up`, then http://localhost:8080.
- Deployment: every push to `main` runs `.github/workflows/deploy.yml`, which builds the site and publishes the `gh-pages` branch.
- See `CLAUDE.md` for the conventions used in this repository.

Theme: [al-folio](https://github.com/alshedivat/al-folio) by Maruan Al-Shedivat and contributors, MIT licence (see `LICENSE`).
