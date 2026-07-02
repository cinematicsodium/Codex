---
name: refactor-constants
description: Refactor a constants.py or equivalent shared constants module so it contains only stable values genuinely shared across multiple modules. Use when Codex needs to audit constants, move module-specific defaults or helper data beside their owners, remove unused constants, update imports, preserve behavior and public APIs, validate the project, and commit each logical move separately.
---

# Refactor Constants

Reduce the shared constants module to true application-wide invariants. Keep ownership local unless multiple modules directly depend on the same stable value.

## Workflow

1. Check the worktree and preserve unrelated edits.
2. Read the constants module and every direct reference before editing.
3. Classify every defined value:
   - Keep it shared only when multiple modules directly use it and it represents stable configuration or a cross-module invariant.
   - Move it beside its sole owning module when it is a path, default, mapping, type alias, display string, helper value, feature-specific setting, or implementation detail.
   - Delete it when it has no real caller.
4. Do not count package re-exports as independent consumers. Do not centralize small literals merely to avoid duplication.
5. Move related constants by concern, update imports and references, and remove obsolete imports after each move.
6. Preserve runtime values, behavior, serialized formats, and public APIs. Re-export from the new owner only when the symbol is genuinely public and doing so does not create a circular import; otherwise report the necessary API change.
7. Avoid creating another constants or configuration layer unless the value still has multiple real consumers.
8. Run the existing tests, linting, type checks, and the smallest relevant smoke or compile check.
9. In a Git repository, commit each major logical group separately with a focused descriptive message. Do not include unrelated pre-existing changes.

## Output

Report:

- What moved and its new owner.
- What remained shared and why.
- The commits created, including hashes and messages.
- Any behavior or public API changes, or explicitly state that there were none.
- Validation results and any unavailable checks.
