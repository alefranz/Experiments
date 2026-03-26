# Migrating From An Existing Repo

This page is a placeholder migration guide designed to keep the staging site close to a real documentation set.

## When to use this path

Use this approach when you already have markdown documentation in another repository and want to rehearse moving it into a dedicated public docs test bed.

## Suggested process

1. Copy the source markdown into `docs/`.
2. Rebuild the navigation in `mkdocs.yml`.
3. Fix internal links so they point to markdown files in the new tree.
4. Run `mkdocs serve` locally.
5. Push to `main` and verify the public deploy.

## Checklist

- page titles render correctly
- nested navigation still works
- fenced code blocks preserve formatting
- internal links resolve after the move
- repository metadata points at the correct public repo

## Example

```text
Old repo
  README.md
  docs/setup.md
  docs/faq.md

New repo
  docs/index.md
  docs/getting-started.md
  docs/troubleshooting.md
```

The point is not to preserve every old path exactly. The point is to validate that the new public docs pipeline behaves correctly.