# My-awesome-global-project

This groups the repositories that are part of my big project.

## Release notes (GitHub Pages)

A web page at the repo root lists and displays all markdown files in `releases/`. It works when the repo is published with **GitHub Pages**.

### Enabling GitHub Pages

1. In your repo on GitHub: **Settings → Pages**.
2. Under **Build and deployment**, choose **Source**: **Deploy from a branch**.
3. Branch: **main** (or your default branch), folder: **/ (root)**.
4. Save. The site will be available at `https://<username>.github.io/My-awesome-global-project/`.

No config is needed in the page: it infers the repo from the URL and uses the GitHub API to list files in `releases/`, then loads each `.md` file and renders it with [marked](https://marked.js.org/).

### Adding new releases

Add a new `.md` file under `releases/` (e.g. `releases/v1.0.12.md`). It will appear in the sidebar after the next deploy. To improve resilience if the API is unavailable, you can also add the filename to the `RELEASES_FALLBACK` array in `index.html`.
