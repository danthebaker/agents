# AGENTS.md

Instructions for AI agents editing this repository. See [README.md](README.md)
for the human-facing overview and [skills/README.md](skills/README.md) for the
per-skill format.

## Rules

- **Skills:** each lives in `skills/<name>/SKILL.md`. The directory basename must
  equal the frontmatter `name:` (lowercase, hyphen-separated). `description:` is
  required and ≤1024 chars.
- **Recipes:** each lives in `recipes/<name>/recipe.yaml` (directory form, not a
  bare YAML file). Required fields: `title` (≤200 chars) and `instructions`
  (≤16 KiB). Structured output goes under `response.json_schema`; sub-recipes
  under `sub_recipes[]` reference sibling recipes by relative `path`.
- **Cross-runtime.** Skills and recipes here run unmodified in Claude Code, Goose,
  and Gatewaze — don't add runtime-specific paths, env assumptions, or
  desktop-only builtins.
- **Media calls stay in the module.** Recipes/skills author *prompts and scripts*;
  the actual Veo / Gemini TTS / ffmpeg calls live in the consuming Gatewaze
  module, never here (mirrors the daily-briefing cover-image split).
