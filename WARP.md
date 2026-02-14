# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## What this repo is
This repository is a **Claude Desktop cowork plugin** implemented entirely as Markdown. It provides two skills (English and Russian) for removing signs of AI-generated text.

## Plugin structure
```
.claude-plugin/
  plugin.json              Plugin manifest (name, version, author)
skills/
  humanizer/
    SKILL.md               English skill - 24 AI writing patterns
  humanizer-ru/
    SKILL.md               Russian skill - 25 patterns + hard prohibitions
commands/
  humanizer.md             /humanizer slash command (English)
  humanizer-ru.md          /humanizer-ru slash command (Russian)
README.md                  English documentation
README_RU.md               Russian documentation
```

## Key files (and how they relate)
- `skills/*/SKILL.md` - The actual skill definitions. Claude reads the YAML frontmatter (name, description, version) and uses the prompt/instructions that follow. These are model-invoked (auto-triggered by context).
- `commands/*.md` - Slash command entry points. YAML frontmatter contains `description`, `argument-hint`, and `allowed-tools`. These are user-invoked via `/humanizer` or `/humanizer-ru`.
- `.claude-plugin/plugin.json` - Plugin manifest with metadata. Plugin auto-discovers `skills/` and `commands/` directories.
- `README.md` / `README_RU.md` - Installation and usage instructions for humans.

When changing behavior/content, treat skill files as the source of truth, and update READMEs to stay consistent.

## Installation
### As plugin (recommended)
```bash
claude plugin add github:teslaproduuction/humanizer_ru
```

### Legacy (Claude Code skills)
```bash
mkdir -p ~/.claude/skills/humanizer-ru
cp skills/humanizer-ru/SKILL.md ~/.claude/skills/humanizer-ru/
```

## How to invoke
- `/humanizer` - English text humanization
- `/humanizer-ru` - Russian text humanization

## Making changes safely
### Versioning (keep in sync)
- `.claude-plugin/plugin.json` has `version` field
- Skill files have `version:` in YAML frontmatter
- READMEs have "Version History" sections

If you bump the version, update all three.

### Editing skill files
- Preserve valid YAML frontmatter formatting and indentation
- Keep the pattern numbering stable (READMEs reference the same numbers)
- Russian skill has HARD PROHIBITIONS section - do not weaken these rules
