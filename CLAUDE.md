This project's AI coding environment is managed by
[ACE](https://github.com/ace-rs/ace). Run `ace` to start a coding session.
Run `ace setup` if not yet configured.

Skills and conventions are provided by the configured school and are symlinked into
`.claude/skills/`. Run `ace config` or `ace paths` to debug configuration issues.

## Repository

This repository publishes reusable, harness-neutral skills in `skills/`. Each skill uses
the common layout `skills/<skill-name>/SKILL.md` with YAML frontmatter and a
self-contained instruction body. The `learn` skill is the primary artifact.
