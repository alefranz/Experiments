# Advanced Patterns

This page is intentionally feature-heavy. Its purpose is to exercise the parts of MkDocs Material that tend to reveal styling or rendering regressions.

## Admonitions

!!! note
    Use notes for neutral contextual information that should stand out without looking like an error.

!!! warning
    If the published site looks different from the local preview, check the deployed branch contents and the configured site URL.

## Content tabs

=== "Local preview"

    ```bash
    pip install mkdocs-material
    mkdocs serve
    ```

=== "GitHub Pages"

    ```bash
    git push origin main
    ```

    Then wait for the docs workflow to publish the site.

## Highlighted code blocks

```yaml hl_lines="1 7 8"
site_name: Experiments

nav:
  - Home: index.md

markdown_extensions:
  - admonition
  - pymdownx.superfences
```

## Tables

| Scenario | What to verify |
|----------|----------------|
| Local preview | Navigation, search, and styling render correctly |
| First public deploy | The site resolves at the expected GitHub Pages URL |
| Subsequent updates | The deployment workflow continues to overwrite stale content |

## HTML plus markdown

<div class="grid cards" markdown>

- **Structured nav**

  Nested sections are useful because they validate more than a single landing page.

- **Readable source**

  Keep markdown straightforward so edits stay easy for both humans and tools.

</div>

## Authoring guidance

- prefer explicit headings over implied structure
- keep code snippets small and runnable where possible
- use tables when comparisons are easier to scan than prose
- use nested pages when you want a meaningful navigation rehearsal