---
description: Start or update today's daily task note in the wiki and load its linked context
---

Work with the daily task note for today. Vault root: `~/.llm-wiki/`.

Procedure:

1. Compute today's date as `YYYY-MM-DD` (from the `Current date:` line in context).
2. Read `~/.llm-wiki/wiki/journal/<YYYY-MM-DD>.md`.
   - If it does not exist, create it by copying the structure of `~/.llm-wiki/wiki/journal/_template.md` (same folder, same `type: journal` frontmatter, `title` = the date).
3. Call `wiki_recall` with the task terms the user gives you so previously filed entity/concept/synthesis/analysis pages related to today's tasks are surfaced.
4. For each task the user lists, record it under `Work` or `University` (both may be present) with a status marker: `[ ]` open, `[x]` done, `[~]` blocked (add the blocker inline). Anything that fits neither stack goes under `Other`.
5. Do not add an `# <date>` H1 — Obsidian renders the filename as the title, so a body H1 duplicates it. Start the body at `## Work`.
6. When a task is closed during the session, mark it `[x]` in the daily note and, if it produced a durable insight, save that with `wiki_retro` and add a link to the new page under `Linked pages` in the daily note.
7. Keep `Linked pages` as the hub: one root-relative Markdown link per related wiki page, e.g. `[Grafana](/entities/grafana.md)`. One daily note may link to many pages; a retro page should also link back to the daily note.
8. Do not duplicate page content into the daily note — link to the page instead.
9. Frontmatter tags: 1-5 entries in `owner` or `owner/subject` form, owners `youwe` | `aberystwyth-university` | `llm-wiki` | `personal`. Daily notes carry owner tags only. Full rules: [llm-wiki](/entities/llm-wiki.md), `WIKI_SCHEMA.md`.

Extra context from the user (may be empty): $@
