# Phase 1 - Repo Skeleton and README - Start Brief

A fresh session should be able to complete this phase from this brief alone.

## Objective
The `RelationshipOS/` directory tree exists with all required subfolders, and a complete
top-level `RelationshipOS/README.md` positions the product and explains how to use the
Markdown system.

## Scope
In scope: create `RelationshipOS/`, `RelationshipOS/Relationships/`,
`RelationshipOS/Templates/`, `RelationshipOS/Logs/`, and author
`RelationshipOS/README.md`. Out of scope: the template files, the assistant instructions,
the example profile, the workflow files (later phases). Placeholder `.gitkeep` files are
fine for empty dirs until later phases fill them.

## What already exists
The repo has the Blueprint scaffold (`docs/`, `reports/`) plus the project-setup docs
(`docs/setup/onboarding.md`, `docs/reference/phase-briefs/`). The `RelationshipOS/` tree
does not exist yet.

## What to inspect first
- `docs/setup/onboarding.md` (the product summary and folder map)
- `/tmp/master-build-*/final-plan.md` if present (the locked plan, Component Roster)

## Files likely to be created or edited
- `RelationshipOS/README.md`
- `RelationshipOS/Relationships/.gitkeep`
- `RelationshipOS/Templates/.gitkeep`
- `RelationshipOS/Logs/.gitkeep`

## Commands likely to be run
- `mkdir -p RelationshipOS/{Relationships,Templates,Logs}`

## What must NOT change
The Blueprint `docs/` and `reports/` placeholder files.

## Install or deployment impact
None.

## Testing requirements
`find RelationshipOS -type d` shows the four directories. `RelationshipOS/README.md`
contains: a one-line positioning statement, a "what it is / what it is not" section, the
folder map, and a "how to use" section (copy-paste a profile plus a workflow template into
any LLM). Grep for em dashes returns nothing.

## Documentation requirements
Update the tracker (Phase 1 checklist) and onboarding "current phase".

## Done criteria
- [ ] `RelationshipOS/` tree with Relationships/, Templates/, Logs/ exists
- [ ] `RelationshipOS/README.md` written with positioning, is/is-not, folder map, usage
- [ ] No em dashes (`grep -RnP "\x{2014}" RelationshipOS` is empty)
- [ ] Tracker updated and pushed
- [ ] Onboarding "current phase" / "next step" updated

## Estimated context size
small

## How to verify completion
`find RelationshipOS -type d` and `grep -c "What it is not" RelationshipOS/README.md`.
