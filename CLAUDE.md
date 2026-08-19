This project's AI coding environment is managed by
[ACE](https://github.com/ace-rs/ace). Run `ace` to start a coding session.
Run `ace setup` if not yet configured.

Skills and conventions are provided by the configured school and are symlinked into
`.claude/skills/`. Run `ace config` or `ace paths` to debug configuration issues.

## Repository

This repository publishes reusable, harness-neutral skills in `skills/`. Each skill uses
the common layout `skills/<skill-name>/SKILL.md` with YAML frontmatter and a
self-contained instruction body. The `learn` skill is the primary artifact.

Whenever skill content is created, revised, or otherwise edited, delegate the editing
to the GPT Sol model through the internal subagent tool at high reasoning effort. The
designated GPT Sol editor may edit skill content directly after loading all applicable
skills, conventions, and standing instructions. Do not use `ace-connect` for this
delegation; edits to standing instructions remain local.
