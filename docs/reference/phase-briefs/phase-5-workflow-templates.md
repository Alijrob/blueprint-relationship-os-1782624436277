# Phase 5 - Workflow Templates - Start Brief

## Objective
The five workflow prompt files exist in `RelationshipOS/Templates/`: Gift_Planner.md,
Date_Planner.md, Conflict_Prep.md, Memory_Update.md, Retrieval.md. Each is an executable
Markdown prompt a user pastes into an LLM alongside a profile.

## Scope
In scope: the five workflow templates. Out of scope: the example profile and the final
validation sweep.

## What already exists
Phases 1 to 4 produced the tree, README, Assistant_Instructions, Profile_Template, memory
log, privacy model, and schema.

## What to inspect first
- `RelationshipOS/Assistant_Instructions.md` (each workflow must point back to it and restate the safety boundaries)
- `RelationshipOS/Templates/Profile_Template.md` (workflows read these sections)
- `RelationshipOS/Logs/Memory_Update_Log.md` (Memory_Update writes rows in this exact shape)

## Files likely to be created or edited
- `RelationshipOS/Templates/Gift_Planner.md`
- `RelationshipOS/Templates/Date_Planner.md`
- `RelationshipOS/Templates/Conflict_Prep.md`
- `RelationshipOS/Templates/Memory_Update.md`
- `RelationshipOS/Templates/Retrieval.md`

## What must NOT change
The profile section order, the log column order, the assistant instructions.

## Install or deployment impact
None.

## Testing requirements
- Gift_Planner: instructs the LLM to assess past hints, preferences, and dislikes to
  generate thoughtful gift ideas.
- Date_Planner: designs outings from preferences, schedule, and boundaries.
- Conflict_Prep: prepares for difficult conversations neutrally; forbids guessing emotional
  states or asserting assumptions as fact; recommends direct human communication.
- Memory_Update: parses unstructured input into the 8-column log row shape.
- Retrieval: queries the profile and log accurately and flags uncertainty.
Each file restates or references the safety boundaries. Grep for em dashes returns nothing.

## Documentation requirements
Update tracker and onboarding.

## Done criteria
- [ ] All five workflow files exist with correct behavior
- [ ] Each references the safety boundaries / Assistant_Instructions
- [ ] Memory_Update output matches the 8-column log shape
- [ ] No em dashes
- [ ] Tracker updated and pushed

## Estimated context size
medium

## How to verify completion
`ls RelationshipOS/Templates/` shows all five files; read each to confirm behavior.
