# Migrating From Another Project

This variant focuses on adapting documentation content from a code-first repository into a docs-first layout.

## Typical adjustments

- replace package-specific branding with repository-neutral wording
- turn large README sections into separate docs pages
- move setup instructions into Getting Started
- move known issues into Troubleshooting
- keep one nested section to validate deeper navigation

## Before and after

| Original shape | Staging shape |
|----------------|---------------|
| One long README | Multiple docs pages |
| Inline screenshots or badges | Optional extras after the pipeline works |
| Ad hoc headings | Ordered nav from `mkdocs.yml` |

## Validation steps

```bash
mkdocs serve
mkdocs build --strict
```

After that, push the branch and confirm GitHub Pages serves the repository path you expect.

## Why keep this page

Even placeholder migration pages are useful here because they test:

- nested URLs
- side navigation grouping
- search indexing across multiple sections
- future expansion room once the staging site proves out