# Xiang He — academic website

A responsive Quarto academic website built from the September 2024 CV, with pages for research, publications, projects, CV, and contact information.

## Preview locally

Install [Quarto](https://quarto.org/docs/get-started/) and run:

```powershell
quarto preview
```

## Publish with GitHub Pages

The included workflow renders and deploys the site whenever `main` is pushed. In the repository's **Settings → Pages**, set **Source** to **GitHub Actions**. The workflow will then publish the `_site` artifact automatically.

The current repository is a project site, so its default Pages URL is expected to be:

`https://hx38324.github.io/my-github-page.github.io/`

## Update later

- Add publication entries in `publications.qmd`.
- Replace the Google Scholar placeholder after creating a profile.
- Replace `assets/Xiang_He_CV_September2024.pdf` and update the CV page when a newer CV is available.
- Update the site URL in `_quarto.yml` if the repository is renamed or a custom domain is added.
