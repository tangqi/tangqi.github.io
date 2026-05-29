# tangqi.github.io

Personal academic website for Qi Tang, built with [MkDocs](https://www.mkdocs.org/)
and a custom theme (in `template/`) derived from the MFEM webpage template.

## Setup

Use a recent Python (3.9+). With a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirement.txt
```

Or with conda:

```bash
conda create -n web python=3.12
conda activate web
pip install -r requirement.txt
```

## Editing

- Clone this repo.
- Edit or add `.md` files in `src/` (and update the `nav` section of `mkdocs.yml`
  if you add a new page).
- Preview locally with `mkdocs serve` (defaults to http://127.0.0.1:8000).
- Publish with `mkdocs gh-deploy`.

## Notes

- Content lives in `src/`; the site is configured via `mkdocs.yml`.
- The custom theme (HTML/CSS/JS) lives in `template/`.
- Pinned dependencies are in `requirement.txt`. This site was modernized off the
  original MkDocs 1.0.4 pin; if a build issue appears after upgrading, check
  `mkdocs --version` and the MkDocs release notes for template API changes.
