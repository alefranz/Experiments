# Experiments — LLM Reference

> This is a self-contained reference for updating this staging documentation site with an LLM or other automated editing tool.

## Objective

Maintain a public MkDocs Material site that is intentionally simple to deploy but rich enough to validate:

- multi-page navigation
- nested sections
- GitHub Pages publishing
- common markdown extensions

## Repository expectations

```text
.
├── .github/workflows/docs.yml
├── docs/
└── mkdocs.yml
```

## Editing rules

| Rule | Guidance |
|------|----------|
| Branding | Use `Experiments` only |
| Purpose | Treat the repo as a staging site for docs pipeline validation |
| Deployment | Preserve the official Pages artifact upload and deploy workflow unless a deliberate change is requested |
| Navigation | Keep at least one nested section to exercise deeper routing |
| Content style | Prefer explicit headings, short paragraphs, tables, and runnable commands |

## Common tasks

### Add a page

1. Create the markdown file under `docs/`.
2. Add it to `nav` in `mkdocs.yml`.
3. Link to it from an existing page if appropriate.
4. Run a local build or preview.

### Update repository metadata

When the repository URL or name changes, update all of these together:

```yaml
site_url:
repo_url:
repo_name:
```

### Validate the setup

```bash
pip install mkdocs-material
mkdocs build --strict
```

## Preferred authoring style

- keep examples concrete
- avoid product-specific claims unless the repo actually owns that product
- use markdown features intentionally so the site meaningfully exercises the theme
- keep wording neutral and staging-oriented