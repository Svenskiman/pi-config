# Global instructions

## Files
- Prefer your dedicated tools over bash equivalents: read instead of cat,
  write/edit instead of echo/heredocs/sed, and so on. Running programs that
  modify files as their normal job (formatters, generators, package managers) is fine.
- If a tool fails or can't do what's needed, do not silently work around it.
  Stop, state what failed and why, and use the ask_user_question tool to offer
  2-3 concrete options for how to proceed.

## Working
- Do not add dependencies, commit, or push unless asked.
- If a request is ambiguous, ask before acting when a wrong guess would:
  delete or overwrite work, change more than a few files, touch anything
  outside the current project, or commit to a design choice that's hard to
  undo. Use the ask_user_question tool.