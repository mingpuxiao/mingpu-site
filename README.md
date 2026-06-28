# mingpu-site

Personal academic website for **Mingpu Xiao**, Ph.D. candidate in Political
Science at UC San Diego. Built with [Hugo](https://gohugo.io/) and deployed to
GitHub Pages.

**Live site:** https://mingpuxiao.github.io/mingpu-site/

## Editing the site

You don't need to touch code for routine updates — see **[UPDATING.md](UPDATING.md)**
for a plain-language guide. In short:

| To change… | Edit… |
|---|---|
| Bio | `content/_index.md` |
| Name, email, advisors, interests, menu | `hugo.yaml` |
| Papers | `data/papers.yaml` |
| Teaching | `data/teaching.yaml` |
| Photos | `data/photos.yaml` (+ images in `static/images/hikes/`) |
| PDFs (CV, papers) | upload to `static/files/` |
| Colors | top of `assets/css/style.css` |

## How deployment works

Every push to the `main` branch triggers the GitHub Actions workflow in
`.github/workflows/deploy.yml`, which builds the site with Hugo and publishes it
to GitHub Pages. No manual step is required. (One-time setup: repository
**Settings → Pages → Source: GitHub Actions**.)

## Running locally (optional)

Requires the **extended** build of Hugo (`brew install hugo`).

```bash
hugo server     # preview at http://localhost:1313/
hugo --gc --minify   # build into ./public
```

## Structure

```
hugo.yaml                 site config, identity, menu
content/_index.md         homepage bio
data/                     papers, teaching, photos (the lists)
assets/css/style.css      all styles (light theme, no external fonts)
layouts/                  HTML templates (custom, no theme)
static/                   images, PDFs, favicons (served as-is)
.github/workflows/        automatic build + deploy
```
