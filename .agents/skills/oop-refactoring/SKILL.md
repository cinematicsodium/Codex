---
name: oop-refactoring
description: Refactor code to use object-oriented design only where it clearly improves readability, maintainability, separation of concerns, or reuse. Use when the user asks to apply OOP, convert procedural code to classes, split responsibilities into objects, or reorganize code with practical OOP while preserving existing behavior, public interfaces, and outputs.
---

# OOP Refactoring

Refactor with OOP where it pays for itself. Preserve behavior first; improve structure second. Prefer the smallest object model that makes the code easier to understand, test, or change.

## Workflow

1. Review the current structure, callers, public APIs, outputs, and file layout before editing.
2. Ask whether OOP is needed at all; skip classes when functions, modules, or existing helpers already solve the problem clearly.
3. Reuse existing project patterns, helpers, and types before introducing new objects.
4. Identify places where classes, encapsulation, abstraction, or composition remove real complexity.
5. Use inheritance, ABCs, or Protocols only when there is a clear practical benefit.
6. Preserve existing features, logic, public interfaces, and outputs unless a change is required; explain any necessary behavior or API change.
7. Create, rename, move, split, merge, or remove files only when it clearly improves maintainability or organization.
8. Remove dead, unused, redundant, or unnecessary files that are part of the refactor scope.
9. Keep imports minimal, consistent, and idiomatic.
10. Validate with the smallest meaningful check available for the project.

## Design Rules

- Let the code earn each class. No class is better than a class that only wraps one function, one constant, or one caller.
- Prefer composition over inheritance unless the hierarchy already exists or is naturally required.
- Do not add pattern-heavy designs, speculative extension points, factories, registries, or layers for future possibilities.
- Keep file structure logical and minimal.
- Prefer fewer files unless splitting responsibilities clearly reduces coupling or cognitive load.
- Use standard library and already-installed dependencies before custom infrastructure.
- Use intention-revealing module, file, class, and method names.
- Add comments only when they explain non-obvious decisions.
- Mark deliberate simplifications with a `ponytail:` comment only when the shortcut has a known ceiling and future upgrade path.
- Match the project language and version.

## Minimalist OOP

- Encapsulate state when shared mutable data or invariants are currently leaking across functions.
- Extract a class when it gives a stable home to behavior plus the data it owns.
- Split a class when separate responsibilities change for different reasons or make testing awkward.
- Merge or delete classes that only pass calls through, mirror data shapes, or exist only to satisfy a pattern.
- Keep public entrypoints stable unless changing them is required for correctness or explicitly requested.
- Fix bugs at the shared root of the object flow, not by adding guards to each caller.

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
