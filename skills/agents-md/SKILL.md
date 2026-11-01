---
name: agents-md
description: Create or update a project's AGENTS.md. Use when starting work in a new repo, at the end of a session, or after the user corrects you.
---

# agents-md — Create or update AGENTS.md

Decide between INIT mode and UPDATE mode before doing anything:
- Starting work in a new repo that has no AGENTS.md yet: INIT mode.
- End of a session, or after a correction, in a repo that already has AGENTS.md: UPDATE mode.

## INIT mode (new repo)

1. Survey the repo before drafting:
   - Read README, CONTRIBUTING, package/build manifests, and CI config.
   - Also read any existing CLAUDE.md, `.cursorrules`, or copilot-instructions files.
   - Note how well-documented the repo is (does the README actually explain setup, or is it a placeholder?).
2. Find the real build/test/lint/typecheck commands and RUN them to verify they work before writing them down.
   - Include how to run a single test file.
3. Draft AGENTS.md containing ONLY what an agent could not quickly discover itself:
   - One-line project description.
   - Verified, copy-pasteable commands.
   - Boundaries: files/dirs never to touch, things never to do.
   - Non-obvious conventions and gotchas, especially where the repo differs from what a model would assume.
   - A definition-of-done checklist.
4. Do NOT include:
   - Directory tours.
   - Tech-stack summaries already visible in manifests.
   - Anything already in the README.
   - Generic advice like "write clean code".
   - Anything already covered by ~/.pi/agent/AGENTS.md.
5. If a subdirectory has genuinely different rules, propose a nested AGENTS.md there rather than growing the root file.
6. If AGENTS.md already exists, switch to UPDATE mode instead of overwriting.
7. Show the full draft, then use ask_user_question to get approval (approve / revise / cancel) before writing.

## UPDATE mode (end of session / after a correction)

1. Review this session for non-obvious learnings:
   - My corrections, failed commands, wrong assumptions, things that took several attempts.
   - Skip one-offs and anything discoverable from the code.
2. Each learning is 1-3 lines, placed in AGENTS.md nearest the relevant code.
   - Preferences that apply to all projects go in ~/.pi/agent/AGENTS.md instead.
3. Check for duplicates and contradictions with existing lines.
4. Also flag existing lines that are now wrong or obsolete (commands that changed, paths that no longer exist) and propose removing them.
5. Show the proposed diff, then use ask_user_question to let me approve, pick which items to keep, or cancel before writing.
