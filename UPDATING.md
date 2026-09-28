# Updating your website

The site is a Hugo static site. All content lives in plain-text files; edit
them, push to GitHub, and the site rebuilds itself in ~2 minutes.

## Where things live

| What | File |
|------|------|
| Bio paragraphs | `content/_index.md` |
| Papers (JMP, working, in progress, publications) | `data/papers.yaml` |
| Teaching | `data/teaching.yaml` |
| Fellowships & awards | `data/awards.yaml` |
| Data projects | `data/projects.yaml` |
| Name, email, tagline, links, menu | `hugo.yaml` |
| CV PDF | `static/files/torola_pamela_CV.pdf` (replace the file, keep the name) |
| Headshot | `static/images/headshot.jpg` (160×160 or larger, square-ish) |
| Colors & styling | `assets/css/style.css` |

## Common tasks

- **Add a paper:** add an entry to `data/papers.yaml` with `section:` set to
  `jmp`, `working`, `progress`, or `publication`. Put the PDF in
  `static/files/` and add `pdf: "/files/name.pdf"`.
- **Mark a paper published:** change its `section:` to `publication` and add
  `venue:` and `year:`.
- **Update the CV:** overwrite `static/files/torola_pamela_CV.pdf`.
- **Change the JMP:** the paper with `section: jmp` gets the highlighted card
  with the abstract shown.

## Preview locally

```
hugo server
```

then open http://localhost:1313.

## Going live (first time)

1. Create a GitHub repo named `USERNAME.github.io` and push this folder.
2. In the repo: Settings → Pages → Source: "GitHub Actions".
3. Set `baseURL` in `hugo.yaml` to `https://USERNAME.github.io/`.
4. Push to `main` — the workflow in `.github/workflows/deploy.yml` builds and
   deploys automatically.
