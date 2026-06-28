# Relationship OS - Onboarding

## What this project is

Relationship OS is a private, portable, AI-assisted relationship memory system: a
modern Rolodex for real human relationships. It stores relationship context (not just
contact details) about the important people in a user's life and lets any standard LLM
act as the interface for retrieval, gift planning, date planning, follow-up reminders,
and conversation preparation.

The value is the structured, user-owned relationship knowledge base, not the AI model.
Plain Markdown files are the source of truth.

This is NOT a dating app, therapy or counseling platform, medical or fertility advisor,
or period tracker.

## What this build delivers (MVP phase)

A self-contained Markdown system, delivered as this GitHub repository:

```
RelationshipOS/
  README.md
  Assistant_Instructions.md
  Relationships/
    Example_Person.md
  Templates/
    Profile_Template.md
    Gift_Planner.md
    Date_Planner.md
    Conflict_Prep.md
    Memory_Update.md
    Retrieval.md
    Privacy_Visibility_Model.md
    Data_Model_Schema.md
  Logs/
    Memory_Update_Log.md
```

No web application code is built in this phase. The future app is represented only by a
data-model schema document (`Templates/Data_Model_Schema.md`).

## Where the code lives

- GitHub: `github.com/Alijrob/blueprint-relationship-os-1782624436277`
- Local (THOTH): `/root/relationship-os`
- Phase tracker: `pagios-ops/trackers/relationship-os-phase-tracker.md`
- Phase briefs: `docs/reference/phase-briefs/`

## How to install / run

There is nothing to install or run as a service. A user clones or downloads the
`RelationshipOS/` folder, opens it in any text editor, and copy-pastes the relevant
profile plus a workflow template into any standard consumer LLM chat window.

## How to deploy

Deployment is distribution of the repository. No server, port, PM2 process, database, or
nginx vhost is involved.

## Required environment variables

None. The system has no runtime and no secrets.

## Important files

- `RelationshipOS/Assistant_Instructions.md` - master system prompt + safety boundaries.
- `RelationshipOS/Templates/Profile_Template.md` - the 11-section profile template.
- `RelationshipOS/Logs/Memory_Update_Log.md` - the 8-column source-tagged memory log.
- `RelationshipOS/Templates/Privacy_Visibility_Model.md` - privacy + visibility model.
- `RelationshipOS/Templates/Data_Model_Schema.md` - schema for the future app.

## Current phase

Phase 1 (Repo skeleton and README) is complete: the `RelationshipOS/` directory tree
(Relationships/, Templates/, Logs/) and the top-level `RelationshipOS/README.md` exist.
Phase 2 (Assistant Instructions and MVP Prompt) is up next. See the tracker.

## Known blockers

None.

## Next likely step

Build Phase 2: author `RelationshipOS/Assistant_Instructions.md` with the runnable MVP
system prompt and all seven safety boundaries.

## Hard rules for every phase

- No em dashes anywhere (use commas, hyphens, colons, parentheses, or periods).
- Markdown is the source of truth; no application code in the MVP.
- Encode the safety boundaries verbatim; the assistant never diagnoses, never asserts
  another person's feelings as fact, never gives medical, therapy, or fertility advice,
  asks before saving, marks sensitive data, and recommends direct communication when
  uncertain.
- Keep enums aligned across the profile template, the memory log, and the schema.
