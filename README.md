# My-awesome-global-project

This groups the repositories that are part of my big project.

## Release notes (GitHub Pages)

A web page at the repo root lists and displays all markdown files in `releases/`. It works when the repo is published with **GitHub Pages**.

### Enabling GitHub Pages

1. In your repo on GitHub: **Settings → Pages**.
2. Under **Build and deployment**, set **Source** to **GitHub Actions** (so the workflow deploys the site).
3. Push to `main` (or run the workflow manually from the **Actions** tab). The site will be at `https://<username>.github.io/My-awesome-global-project/`.

A workflow in `.github/workflows/deploy-pages.yml` runs on every push to `main` and on manual trigger; it uploads the repo (including `index.html` and `releases/`) and deploys it to GitHub Pages.

No config is needed in the page: it infers the repo from the URL and uses the GitHub API to list files in `releases/`, then loads each `.md` file and renders it with [marked](https://marked.js.org/).

### Adding new releases

Add a new `.md` file under `releases/` (e.g. `releases/v1.0.12.md`). It will appear in the sidebar after the next deploy. To improve resilience if the API is unavailable, you can also add the filename to the `RELEASES_FALLBACK` array in `index.html`.
