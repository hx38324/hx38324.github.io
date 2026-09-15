# Xiang He CV workflow

This setup is designed so that your CV and Quarto personal website share the same publication database.

## Recommended repository structure

```text
my-github-page.github.io/
├── cv/
│   ├── cv.tex
│   └── publications.bib
├── publications.qmd
├── cv.qmd
└── assets/
    └── cv/
        └── Xiang_He_CV.pdf
```

## Normal update workflow

1. Edit `cv/cv.tex` when education, research, skills, awards, or experience changes.
2. Edit only `cv/publications.bib` when a paper is submitted, accepted, or published.
3. Compile the CV:

```bash
cd cv
latexmk -pdf -interaction=nonstopmode cv.tex
```

Because the template uses `biblatex`, `latexmk` will invoke `biber` automatically when available.

4. Copy the generated PDF to the website asset directory:

```bash
cp cv.pdf ../assets/cv/Xiang_He_CV.pdf
```

5. In Quarto, point the publications page to the same file:

```yaml
bibliography: cv/publications.bib
nocite: |
  @*
```

6. Render and publish the site normally.

## Why this is better than manually maintaining a web CV

- `publications.bib` becomes the single source of truth for publications.
- Your downloadable PDF is always the current CV rather than a dated 2024 attachment.
- The website can remain concise while the PDF contains the complete academic record.
- You can create a separate one-page resume without changing the academic CV.

## Suggested naming convention

Use a stable website URL such as:

```text
assets/cv/Xiang_He_CV.pdf
```

Do not put the year in the public filename. That way links on your website, LinkedIn, applications, and QR codes never need to change. Git preserves the version history for you.

## Publications status

For accepted papers, use:

```bibtex
note = {Accepted}
```

When the paper is formally published, replace/update volume, pages/article number, DOI, and remove `Accepted`.

## Career-fair resume

Keep the resume separate from this CV. A good structure is:

```text
resume/
├── resume.tex
└── Xiang_He_Resume.pdf
```

The resume should be tailored to each job family; the academic CV should remain comprehensive and relatively stable.
