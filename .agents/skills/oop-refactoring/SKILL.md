---
name: oop-refactoring
description: Refactor code to use object-oriented design only where it clearly improves readability, maintainability, separation of concerns, or reuse. Use when the user asks to apply OOP, convert procedural code to classes, split responsibilities into objects, or reorganize code with practical OOP while preserving existing behavior, public interfaces, and outputs.
---

# OOP Refactoring

Refactor with OOP where it pays for itself. Preserve behavior first; improve structure second.

## Workflow

1. Review the current structure, callers, public APIs, outputs, and file layout before editing.
2. Identify places where classes, encapsulation, abstraction, or composition remove real complexity.
3. Use inheritance, ABCs, or Protocols only when there is a clear practical benefit.
4. Preserve existing features, logic, public interfaces, and outputs unless a change is required; explain any necessary behavior or API change.
5. Create, rename, move, split, merge, or remove files only when it clearly improves maintainability or organization.
6. Remove dead, unused, redundant, or unnecessary files that are part of the refactor scope.
7. Keep imports minimal, consistent, and idiomatic.
8. Validate with the smallest meaningful check available for the project.

## Design Rules

- Prefer composition over inheritance unless the hierarchy already exists or is naturally required.
- Do not add pattern-heavy designs, speculative extension points, or unnecessary layers.
- Keep file structure logical and minimal.
- Use intention-revealing module, file, class, and method names.
- Add comments only when they explain non-obvious decisions.
- Match the project language and version.

## Type Hints

Use idiomatic type hints for the language version:

- Use built-in types directly where supported: `str`, `int`, `list`, `dict`, `tuple`, `set`.
- Prefer modern built-in generic syntax where supported: `list[str]`, `dict[str, Any]`.
- Import from typing only for non-built-in constructs such as `Any`, `Callable`, `Iterable`, `Mapping`, `Sequence`, `Protocol`, `TypeVar`, `Generic`, `Literal`, `TypedDict`, `ClassVar`, `Final`, and `overload`.

## Response

When reporting the refactor, include:

1. Final file structure.
2. Refactored code for each changed or new file when the user asks for code in chat.
3. Brief design explanation.
4. OOP principles applied and why.
5. Files added, removed, renamed, merged, or reorganized.
