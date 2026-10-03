# S M Samiul Islam — Portfolio

Personal academic portfolio built with [Hugo Blox](https://hugoblox.com) (Academic CV template) and deployed to GitHub Pages.

## Where things live

| What | File |
|---|---|
| Name, bio, education, experience, skills, certifications, links | `data/authors/me.yaml` |
| Profile photo | `assets/media/authors/me.jpg` (square, ≥ 400px) |
| Homepage sections | `content/_index.md` |
| Experience page | `content/experience.md` |
| Projects | `content/projects/<slug>/index.md` (+ optional `featured.jpg`) |
| Navigation | `config/_default/menus.yaml` |
| Site name, theme, SEO | `config/_default/params.yaml` |
| CV source / PDF | `cv/format_1.tex` → `static/uploads/resume.pdf` |

## Local development

Requires Hugo Extended 0.162.0 (version pinned in `hugoblox.yaml`), Go, Node 22 and pnpm.

```sh
pnpm install
pnpm dev          # http://localhost:1313
pnpm build        # production build into public/
```

## Updating the CV PDF

The deploy workflow compiles `cv/format_1.tex` with Tectonic and publishes it as `uploads/resume.pdf`, so the **Download CV** button always matches the `.tex` in the repo. To update the CV after editing it in Overleaf:

1. Copy the full source from Overleaf.
2. On GitHub, open `cv/format_1.tex` and click the pencil icon. Paste the source and commit to `main`.
3. Wait 1–2 minutes for the site to redeploy.

`cv/format_1.tex` has a `\publictrue` switch that hides the phone number and street address on the website copy. Keep it set to `\publictrue` in the repo, and use `\publicfalse` in Overleaf for the full version you send directly.

The committed `static/uploads/resume.pdf` is only a fallback for local previews.

`cv/resume.cls` is Trey Hunner's resume class with one change: the header prints in `\AfterEndPreamble` so that `\href` works inside `\address`.

## Deployment

Pushing to `main` runs `.github/workflows/deploy.yml`, which builds the site and publishes it to GitHub Pages. In the repo settings, set **Pages → Source** to **GitHub Actions**.

## Local template fix

`layouts/_partials/functions/build_links.html` overrides the blox module's partial. The upstream version seeds a scratch map with `(dict)`, which hits a nil map under Hugo 0.162 and breaks any page with `links:`. Delete the override once upstream fixes it.
