---
name: simplify-constants
description: Refactor a constants.py or equivalent shared constants module using both Ponytail minimalism and the refactor-constants workflow. Use when Codex needs to remove unused constants, move single-owner values beside their owners, retain only true cross-module invariants, preserve behavior and public APIs, and make the smallest complete change.
---

# Simplify Constants

Use both skills before editing:

1. Activate the installed `ponytail` skill at `full` intensity.
2. Load and follow `.agents/skills/refactor-constants/SKILL.md`.

Let `refactor-constants` define the domain workflow, validation, commits, and final report. Let Ponytail govern implementation choices: question whether each shared value needs to exist, reuse existing owners and project patterns, prefer deletion over relocation, avoid replacement constants layers, and make the fewest-file change that fully preserves behavior.

Do not apply `refactor-constants` to unrelated refactoring. Do not let minimalism override explicit requirements, compatibility, validation, or the source skill's requirement to commit each major logical group separately.
