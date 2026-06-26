---
name: file-to-skill
description: Convert a source text, markdown, prompt, or instruction file into a proper repo-scoped Codex skill. Use when the user asks to read a file, turn it into a skill, place it under .agents/skills, create agents/openai.yaml metadata, register it in the repo reference files, and optionally remove the original scratch file.
---

# File to Skill

Turn one source file into the smallest valid skill this repo needs.

## Workflow

1. Read the source file completely.
2. Inspect existing repo skill conventions:
   - `.agents/skills/<skill-name>/SKILL.md`
   - `.agents/skills/<skill-name>/agents/openai.yaml`
   - `README.md`
   - `AGENTS.md`
3. Choose a concise hyphen-case skill name from the source file's purpose.
4. Initialize the skill with the skill-creator `init_skill.py` script.
5. Replace the generated `SKILL.md` template with concise instructions distilled from the source file.
6. Keep only required resources. Do not create `references/`, `scripts/`, or `assets/` unless the source file needs them.
7. Keep `agents/openai.yaml` to UI-facing metadata unless extra fields were explicitly requested.
8. Register the skill in existing reference files only. In this repo, update `README.md`; do not add custom registries.
9. Remove the original scratch file only when the source has been fully converted and the file is not otherwise needed.
10. Validate the new skill with `quick_validate.py`.

## SKILL.md Rules

- Use YAML frontmatter with only `name` and `description`.
- Put trigger conditions in `description`; the body is loaded only after selection.
- Preserve the source file's real intent, not its temporary formatting.
- Rewrite prompt-style text as imperative workflow guidance for a future Codex agent.
- Keep the body lean; move large supporting material into `references/` only when needed.

## Metadata Rules

Create `agents/openai.yaml` with:

- `interface.display_name`: readable title.
- `interface.short_description`: short UI blurb.
- `interface.default_prompt`: one sentence that explicitly mentions `$skill-name`.

## Validation

Run:

```bash
python3 /Users/Joey/.codex/skills/.system/skill-creator/scripts/quick_validate.py <path-to-skill>
```

Report the created files, registration change, scratch-file handling, and validation result.
