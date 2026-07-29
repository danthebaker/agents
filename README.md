# Agents

Reusable agent resources (skills, recipes, prompts) for danthebaker / Gatewaze
modules. Mirrors the structure of `gatewaze/lf-agents` so the same `SKILL.md`
and `recipe.yaml` files run unmodified in Claude Code, Goose, and Gatewaze.

This repo is consumed by Gatewaze as an **AI recipe/skill source**
(`Admin → AI → Agent Sources` / `Skill Sources`, `path_prefix: recipes` and
`skills`). A Gatewaze module binds one of its AI use-cases to a recipe here via
`ai_use_cases.recipe_source_id + recipe_file_path`, and the recipe's
`instructions` auto-load the matching skill body.

## Repository structure

```text
agents/
├── skills/
│   └── <skill-name>/SKILL.md
├── recipes/
│   └── <recipe-name>/recipe.yaml
├── prompts/
│   └── ...
└── docs/
    └── ...
```

## Contents

- `skills/` — Agent Skills: reusable domain expertise and authoring contracts.
- `recipes/` — Repeatable Goose workflows (parent + sub-recipes, structured output).
- `prompts/` — Reusable prompt templates.
- `docs/` — Supporting documentation.

## Current agents

### Vehicle Video (module: `vehicle-video`)

Three recipe/skill pairs that drive the AI steps of the Vehicle Video module
(listing URL → sectioned storyboard → per-section AI video clips → voiceover →
final MP4). The module owns the media-API calls (Veo, Gemini TTS, ffmpeg); these
recipes/skills own the *authoring* — exactly the split `daily-briefing` uses
(recipe/skill produce the prompt; module code makes the Gemini call).

- `vehicle-video-script` — vision model reads the photos + scraped details and
  emits a **sectioned storyboard** (exterior / profile / interior / detail / …),
  each section with a chosen photo, scene title, 15–20-word narration, and a
  camera direction. This is the cheap, text-only first gate the operator reviews.
- `vehicle-video-clip-prompt` — shapes one approved section into a clean **Veo
  generation prompt** (smooth, subtle camera motion; keep the real vehicle). The
  module calls Veo with the result; the operator approves/regenerates each clip.
- `vehicle-video-voiceover` — turns the approved sections' narration (in final
  order) into one flowing **TTS-ready voiceover script**. The module calls Gemini
  TTS with the result during final composition.
