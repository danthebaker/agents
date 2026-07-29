# skills/

Agent Skills for danthebaker / Gatewaze modules.

## Layout

Each skill lives in its own directory. The directory basename **is** the skill's
canonical identifier (lowercase, hyphen-separated, no leading/trailing/consecutive
hyphens). The `SKILL.md` file inside each directory holds the frontmatter + body.

```text
skills/
├── vehicle-video-script/
│   └── SKILL.md
├── vehicle-video-clip-prompt/
│   └── SKILL.md
└── vehicle-video-voiceover/
    └── SKILL.md
```

Sibling files (under `assets/`, `references/`, `scripts/`, or the skill root) are
recorded as resource paths on the skill row but are inert at runtime in v1.

## Skill format

Skills conform to the [Agent Skills specification](https://agentskills.io/specification.md).

Required frontmatter:
- `name` — lowercase-hyphen string, must equal the directory basename.
- `description` — non-empty string, ≤1024 chars.

Optional passthrough fields: `metadata` (flat string→string map), `license`,
`compatibility`, `when_to_use`, `allowed-tools`.

## Cross-runtime

The same `SKILL.md` files run in Claude Code (`~/.claude/skills/<name>/`), Goose
(`~/.agents/skills/`, `.goose/skills/`, …), and Gatewaze (registered as a skill
source under **Admin → AI → Skill Sources** with `path_prefix: skills`).

## Adding a skill

1. Create `skills/<skill-name>/SKILL.md`.
2. Frontmatter: required `name` (matching the directory basename) + `description`.
3. Write the body — it becomes the system-prompt fragment loaded into context
   whenever a use case binds the skill.
4. Commit + push. Gatewaze syncs on a cron (≈5 min); a configured webhook triggers
   an instant resync.
