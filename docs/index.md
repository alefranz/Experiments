---
hide:
  - navigation
---

# Experiments

## Docs staging without surprises

**Experiments** is a public-facing test bed for validating the docs toolchain before it is reused elsewhere.
The goal is simple: exercise the full MkDocs Material plus GitHub Pages flow with realistic structure and styling.

<div class="grid cards" markdown>

-   :material-rocket-launch:{ .lg .middle } **Close to production**

    ---

    Uses the same Material theme, nested navigation, and GitHub Pages deployment flow.
    Good for checking whether the publishing path behaves as expected.

-   :material-file-document-multiple:{ .lg .middle } **Real docs surface**

    ---

    Includes multiple sections, nested pages, admonitions, tabs, tables, and code blocks.
    Enough structure to catch integration issues early.

-   :material-source-branch:{ .lg .middle } **Simple workflow**

    ---

    Push to `main`, let GitHub Pages deploy from the official Actions workflow,
    and verify the site updates without maintaining a `gh-pages` branch.

-   :material-robot:{ .lg .middle } **LLM-friendly**

    ---

    The content is intentionally explicit and predictable.
    It is easy to rewrite, expand, or regenerate with coding assistants.

</div>

## What this site validates

| Area | What is being tested |
|------|----------------------|
| Theme | MkDocs Material configuration, palette, icons, and search |
| Navigation | Top-level pages plus nested sections under Migration |
| Markdown features | Admonitions, tabs, tables, fenced code blocks, and anchors |
| Deployment | Official GitHub Pages artifact upload and deploy actions |

## Quick start

```bash
pip install mkdocs-material
mkdocs serve
```

Then open the local preview and verify navigation, search, code copy buttons, and nested pages.

## Next steps

- [Getting Started](getting-started.md) for local preview and deployment checks
- [API Guide](api-guide.md) for the docs structure and config surface
- [Advanced Patterns](advanced-patterns.md) for feature-heavy markdown examples
- [LLM Reference](migration/llm-prompt.md) for a reusable editing prompt

## Status

This site exists to validate the documentation pipeline on a public repository before reusing the same setup elsewhere.

Current deployment marker: **Official Pages workflow test - March 2026**.