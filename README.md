# notion-html-sync-test

Experiment repo, not a real project. Testing whether Notion's GitHub integration can
display and/or edit HTML files that live in a GitHub repo — either direction:

- GitHub is the source of truth, Notion just displays the files (view-only sync), or
- Notion itself edits the files via its GitHub connection and pushes commits back.

## Contents

Five self-contained HTML docs under `docs/`, each stressing a different HTML feature so it's
easy to tell at a glance what did or didn't survive the sync:

| File | Tests |
|---|---|
| `01-basic-text.html` | Plain headings/paragraphs/inline formatting — the baseline case |
| `02-table.html` | A structured `<table>` with an inline `<style>` block |
| `03-list-links.html` | Nested ordered lists and hyperlinks (including a same-page anchor) |
| `04-styled-card.html` | Heavy CSS — gradients, shadows, dark palette |
| `05-media-code.html` | Inline SVG image + a preformatted code block |

Each file ends with a visible `Marker: DOC-N-...` line so a glance confirms which file loaded.

## What to check

1. Point Notion's GitHub connection at this repo and see which of the five it can display at all.
2. Note which HTML/CSS features survive (table, style block, SVG, code block) vs. get stripped
   or flattened to plain text.
3. Try editing one file's marker text from inside Notion — does a commit land in this repo?
4. Try editing one file's marker text directly in GitHub — does Notion's view pick it up, and
   how fast?
