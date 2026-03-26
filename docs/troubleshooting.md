# Troubleshooting

Common failures in this setup usually come from one of three places: local environment issues, GitHub Pages publishing problems, or a mismatch between repository metadata and the deployed path.

## `mkdocs` command not found

Install the theme package first:

```bash
pip install mkdocs-material
```

If you are using a virtual environment, make sure it is activated in the shell where you run `mkdocs serve`.

## Site publishes but assets look broken

The most common cause is an incorrect `site_url` or an unexpected repository path.

Check that `mkdocs.yml` points to the repository-specific GitHub Pages URL:

```yaml
site_url: https://alefranz.github.io/Experiments/
```

If the repository name changes, update `site_url`, `repo_url`, and `repo_name` together.

## Workflow succeeds but no site appears

Typical causes:

- GitHub Pages is not enabled for the repository
- the published branch has not been selected in repository settings
- the first deployment has not finished propagating yet

## Navigation links 404

Check the file names in `docs/` against the entries under `nav` in `mkdocs.yml`.
MkDocs expects those paths to match exactly.

## Search or tabs do not render correctly

Make sure the required markdown extensions are still enabled:

```yaml
markdown_extensions:
  - admonition
  - pymdownx.details
  - pymdownx.superfences
  - pymdownx.tabbed:
      alternate_style: true
```

## Local preview differs from the deployed site

Compare these two things first:

- the committed contents of `mkdocs.yml`
- the exact workflow command used for deployment

If the workflow succeeds but the live site does not change, confirm the repository Pages source is set to GitHub Actions and not branch-based publishing.