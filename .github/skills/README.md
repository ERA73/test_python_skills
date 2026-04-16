# Skills (Agent Playbooks)

This folder is the canonical registry of all repository skills.

Any Agent should discover skills by scanning `.github/skills/**` and reading this
file first.

## Agent Discovery Contract

Use these rules to discover skills deterministically:

1. Start at `.github/skills/README.md`.
2. Recursively scan subfolders in `.github/skills/`.
3. Treat every numbered markdown file (`NN-name.md`) as a skill step.
4. Use `00-overview.md` in each skill family as the entrypoint.
5. Treat `templates/` and `config/` as supporting assets.

If this README and folder contents diverge, the folder contents are the source
of truth.

## Current Skills Index

### ETL Family

Entrypoint:
- `.github/skills/etl/00-overview.md`

Ordered steps:
- `.github/skills/etl/10-extract.md`
- `.github/skills/etl/20-transform.md`
- `.github/skills/etl/30-load.md`
- `.github/skills/etl/40-quality.md`
- `.github/skills/etl/50-testing.md`
- `.github/skills/etl/60-observability.md`
- `.github/skills/etl/70-style-and-structure.md`
- `.github/skills/etl/80-docstring.md`

Supporting assets:
- `.github/skills/etl/templates/`
- `.github/skills/etl/config/`

## How Developers Can Prompt Agents

Examples:
- "Follow `.github/skills/etl/00-overview.md` to create a new ETL"
- "Apply `.github/skills/etl/20-transform.md` to the `users_daily` ETL"
- "Validate with `.github/skills/etl/templates/pr_checklist.md`"

## Maintenance Rules

When adding or changing skills:

1. Keep numbered step files ordered by execution flow.
2. Update this README index in the same change.
3. Prefer stable, descriptive filenames.
4. Keep `00-overview.md` up to date as the family entrypoint.