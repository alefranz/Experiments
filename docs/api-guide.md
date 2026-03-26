# API Guide

This page documents the public surface of the docs staging setup rather than a product API.

## Core files

### `mkdocs.yml`

The top-level configuration controls the site metadata, theme, navigation, markdown extensions, and social links.

| Area | Purpose |
|------|---------|
| `site_*` | Branding and canonical site URL |
| `theme` | Material theme settings and palette |
| `nav` | Navigation order and nesting |
| `markdown_extensions` | Feature enablement for richer authoring |
| `extra.social` | Repository link in the header/footer |

### `docs/`

Contains the markdown source rendered into the published site.

| File | Role |
|------|------|
| `index.md` | Landing page with cards and overview |
| `getting-started.md` | Local setup and deployment flow |
| `api-guide.md` | Configuration and structure reference |
| `advanced-patterns.md` | Markdown feature showcase |
| `troubleshooting.md` | Common setup and deployment issues |
| `migration/*` | Nested pages to validate section navigation |

### `.github/workflows/docs.yml`

Builds the site on every push to `main`, uploads the generated artifact, and deploys it with the official GitHub Pages actions.

## Navigation contract

The site keeps a deliberately non-trivial navigation tree:

- top-level pages for primary documentation
- a nested Migration section
- stable ordering controlled from `mkdocs.yml`

That structure is useful because flat sites rarely expose path or navigation issues.

## Enabled markdown features

The configuration enables the features below so the site tests more than plain markdown:

| Feature | Why it matters |
|---------|----------------|
| Admonitions | Validates styled callouts |
| Superfences | Supports richer fenced blocks |
| Tabbed content | Exercises interactive content rendering |
| Highlight with anchors | Checks line-anchor generation |
| Tables | Verifies common structured content |
| TOC permalinks | Confirms heading anchors work |

## Minimal local workflow

```bash
pip install mkdocs-material
mkdocs serve
```

## Minimal publish workflow

The workflow is responsible for deployment. Local validation should stop at build time:

```bash
mkdocs build --strict
```

If this succeeds locally and inside GitHub Actions, the documentation pipeline is behaving as expected.