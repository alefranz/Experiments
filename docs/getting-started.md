# Getting Started

## Installation

Install the same documentation toolchain used by the staging site:

```bash
pip install mkdocs-material
```

From the repository root, start a local preview:

```bash
mkdocs serve
```

By default, the local site is available at `http://127.0.0.1:8000`.

!!! tip "Testing the full path"
    For a meaningful GitHub Pages rehearsal, check all of the following:

    - the site renders locally with `mkdocs serve`
    - the navigation includes nested pages under Migration
    - the `docs.yml` workflow runs successfully on `main`
    - the published site resolves under the repository-specific path

## Project layout

```text
.
├── .github/
│   └── workflows/
│       └── docs.yml
├── docs/
│   ├── index.md
│   ├── getting-started.md
│   ├── api-guide.md
│   ├── advanced-patterns.md
│   ├── troubleshooting.md
│   └── migration/
│       ├── from-moq.md
│       ├── from-nsubstitute.md
│       └── llm-prompt.md
└── mkdocs.yml
```

## First edit

Change a page title or paragraph, save the file, and confirm the local preview reloads.

```markdown
# Home

This is a staging documentation site.
```

## Deploying to GitHub Pages

The workflow in `.github/workflows/docs.yml` now follows the official GitHub Pages deployment pattern:

```yaml
- uses: actions/configure-pages@v5
- uses: actions/setup-python@v5
  with:
    python-version: '3.x'

- run: pip install mkdocs-material
- run: mkdocs build --strict
- uses: actions/upload-pages-artifact@v3
- uses: actions/deploy-pages@v4
```

That keeps the deployment inside the workflow instead of pushing generated files to a separate branch.

## Recommended checks

- open every page once to confirm the nav resolves correctly
- use search to verify the index builds properly
- inspect code blocks to confirm copy buttons appear
- verify the published URL includes the repository name segment
- confirm the home page status shows `Official Pages workflow test - March 2026`