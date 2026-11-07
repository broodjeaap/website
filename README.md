# website

The main website for broodjeaap.net

Plain HTML + CSS, no build step. Everything served lives in `site/`:

- `site/index.html`: home page with the project cards
- `site/projects/<slug>/index.html`: one page per project
- `site/img/<slug>/`: screenshots
- `site/style.css`: the only stylesheet (follows the OS light/dark setting)

Preview locally: `python3 -m http.server 8000 -d site`

Adding a project: copy an existing project page, then add a card to `site/index.html`.

The `Dockerfile` copies `site/` into nginx.

## CI

`.github/workflows/docker-publish.yml` runs on the GitHub mirror of this repo. Every push to `master` (and every `v*.*.*` tag) builds the `Dockerfile` and pushes the image to `ghcr.io/<owner>/<repo>`.
