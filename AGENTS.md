# AGENTS.md

## Purpose
This file defines how agents should operate in this repository,
including how to discover and apply skills.

## Skill Discovery (Required)
Use this deterministic process to find skills:

1. Start at `.github/skills/README.md`.
2. Recursively scan `.github/skills/` for skill families.
3. Treat numbered markdown files (`NN-name.md`) as ordered skill steps.
4. Use `00-overview.md` as the entrypoint for each family.
5. Treat `templates/` and `config/` as supporting assets, not entrypoints.

If this file and the skill folder contents diverge,
folder contents are the source of truth.

## Current Skill Location
- Canonical registry: `.github/skills/`
- Current family entrypoint: `.github/skills/etl/00-overview.md`

## Skill Selection Rules
When a task arrives, select skills in this order:

1. Match task domain to family overview (`00-overview.md`).
2. Follow numbered steps in ascending order
	unless the user asks for a specific step.
3. Use templates/checklists from `templates/`
	during implementation and review.

## Developer Prompting Examples
- Follow `.github/skills/etl/00-overview.md` to build a new ETL flow.
- Apply `.github/skills/etl/20-transform.md` for transformation rules.
- Validate with `.github/skills/etl/templates/pr_checklist.md`
	before finalizing changes.

## Maintenance
When adding or updating skills:

1. Keep numbered steps ordered by execution flow.
2. Update `.github/skills/README.md` in the same change.
3. Keep names stable and descriptive.
4. Keep each family's `00-overview.md` current.
