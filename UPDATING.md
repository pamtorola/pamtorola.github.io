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
| CV PDF | not on the site right now; see "Held back" below |
| Headshot | `static/images/headshot.jpg` (160×160 or larger, square-ish) |
| Colors & styling | `assets/css/style.css` |

## Common tasks

- **Add a paper:** add an entry to `data/papers.yaml` with `section:` set to
  `jmp`, `working`, `progress`, or `publication`. Put the PDF in
  `static/files/` and add `pdf: "/files/name.pdf"`.
- **Mark a paper published:** change its `section:` to `publication` and add
  `venue:` and `year:`.
- **Change the JMP:** the paper with `section: jmp` gets the highlighted card
  under the "Job market paper" heading.

## Preview locally

```
hugo server
```

then open http://localhost:1313.

## Held back on purpose (Sept 2026)

The public site deliberately omits things. Each is one small edit to restore:

- **Abstracts.** Stripped out of `data/papers.yaml` and parked in
  `../Drafts/site_abstracts_held.yaml`. They were removed from the source file,
  not just the template, because the repo is public and GitHub shows source.
  Paste the blocks back and re-add the `<details>` block in `layouts/index.html`.
  Co-authored abstracts must be the official text, verbatim.
- **CV.** The `cv:` param in `hugo.yaml` is commented out, the menu item is
  gone, and the hero button is wrapped in `{{ with site.Params.cv }}`. The
  authoritative CV is the Overleaf project `Torola_CV_JM2026`, not this repo.
  To put it back: drop the PDF in `static/files/`, uncomment `cv:`, re-add the
  menu entry.
- **JMP draft link.** Add `pdf:` to the `jmp` entry in `data/papers.yaml`.

## Publishing a change

The repo is `https://github.com/pamtorola/pamtorola.github.io` (public), Pages
source is set to "GitHub Actions". Any push to `main` rebuilds
https://pamtorola.github.io in about two minutes, via
`.github/workflows/deploy.yml`. Commit and push from GitHub Desktop, or from a
shell in this folder.

Note: the workflow only runs on push (and manual dispatch from the Actions
tab). Changing a Pages setting does not by itself trigger a build.
