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

Phases 1 through 5 are complete. Phase 1 built the `RelationshipOS/` directory tree
(Relationships/, Templates/, Logs/) and the top-level `RelationshipOS/README.md`. Phase 2
authored `RelationshipOS/Assistant_Instructions.md`, which holds the runnable master system
prompt (the "You are my Relationship Memory Assistant" block), all seven safety boundaries,
and the eight memory-structuring fields (Person, Category, Memory, Source, Date, Confidence,
Sensitivity, Visibility). Phase 3 authored `RelationshipOS/Templates/Profile_Template.md`, the
11-section profile template (Basic Information; Preferences; Dislikes; Gift Ideas;
Communication Style; Relationship Notes; Goals; Health and Wellness; Dates and Events;
Boundaries; AI Instructions), with a strictly non-clinical Health and Wellness section, and
`RelationshipOS/Logs/Memory_Update_Log.md`, the 8-column source-tagged memory log (Person,
Category, Memory, Source, Date, Confidence, Sensitivity, Visibility) with enum guidance
(Confidence High/Medium/Low; Sensitivity Normal/Sensitive/Highly Sensitive; Visibility
Private/Shared/Suggested/Archived). Phase 4 authored
`RelationshipOS/Templates/Privacy_Visibility_Model.md` (the Sensitivity values
Normal/Sensitive/Highly Sensitive, the four Visibility values
Private/Shared/Suggested/Archived, partner-controlled sharing, and opt-in shared wellness
context framed respectfully) and `RelationshipOS/Templates/Data_Model_Schema.md` (the
future-app schema as Markdown tables for six entities: Person, Memory, Category, Visibility,
Sensitivity, Source, with enums matching the memory log and Category names matching the
profile template). Phase 5 authored the five workflow templates under
`RelationshipOS/Templates/` (`Gift_Planner.md`, `Date_Planner.md`, `Conflict_Prep.md`,
`Memory_Update.md`, `Retrieval.md`). Each is an executable Markdown prompt the user pastes into
any standard LLM alongside the master system prompt and a person's profile: Gift_Planner assesses
past hints, preferences, and dislikes to propose thoughtful gift ideas; Date_Planner designs
outings from preferences, schedule, and boundaries; Conflict_Prep prepares for difficult
conversations neutrally, forbids guessing emotional states or asserting assumptions as fact, and
recommends communicating directly with the person; Memory_Update parses unstructured input into
the exact 8-column log row shape (Person, Category, Memory, Source, Date, Confidence, Sensitivity,
Visibility); and Retrieval queries the profile and log and flags uncertainty when data is missing,
unclear, or conflicting. Every workflow restates the seven safety boundaries and points back to
`Assistant_Instructions.md`. Phase 6 (Example Profile and Final Validation Sweep) is up next. See
the tracker.

## Known blockers

None.

## Next likely step

Build Phase 6: populate `Relationships/Example_Person.md` fully (all 11 sections, non-clinical
Health and Wellness) and run the final validation sweep (repo-wide em-dash check empty, enums
consistent across template, log, schema, example, directory tree matches the Component Roster).
Note the two Visibility enum sets still need reconciliation: the memory log and the schema use
Private/Shared/Suggested/Archived (per the frozen contracts) while `Assistant_Instructions.md`
still lists Private/Partner-Shared/Shared.

## Hard rules for every phase

- No em dashes anywhere (use commas, hyphens, colons, parentheses, or periods).
- Markdown is the source of truth; no application code in the MVP.
- Encode the safety boundaries verbatim; the assistant never diagnoses, never asserts
  another person's feelings as fact, never gives medical, therapy, or fertility advice,
  asks before saving, marks sensitive data, and recommends direct communication when
  uncertain.
- Keep enums aligned across the profile template, the memory log, and the schema.
