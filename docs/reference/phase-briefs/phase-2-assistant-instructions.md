# Phase 2 - Assistant Instructions and MVP Prompt - Start Brief

## Objective
`RelationshipOS/Assistant_Instructions.md` exists and contains the complete master system
prompt (the runnable "You are my Relationship Memory Assistant" prompt) and explicitly
encodes all seven required safety boundaries.

## Scope
In scope: the assistant role, the runnable MVP system prompt, and the seven safety
guardrails, plus how the assistant should structure and source-tag memories. Out of scope:
the profile template, workflow files, schema, example profile.

## What already exists
Phase 1 created the `RelationshipOS/` tree and README.

## What to inspect first
- `RelationshipOS/README.md`
- `docs/setup/onboarding.md` (the safety boundary list at the bottom)

## Files likely to be created or edited
- `RelationshipOS/Assistant_Instructions.md`

## Commands likely to be run
- none beyond writing the file

## What must NOT change
The README and folder structure.

## Install or deployment impact
None.

## Testing requirements
The file must contain all SEVEN safety boundaries, each stated explicitly:
1. Never diagnose medical or psychological conditions.
2. Never assert another person's feelings as objective fact.
3. Never provide medical, therapeutic, or fertility advice.
4. Always ask for confirmation before saving or logging new information.
5. Identify and isolate sensitive data; never use it casually.
6. Recommend direct human communication when relationship uncertainty is high.
7. Keep all memories structured and source-tagged.
The file must also contain a clearly delimited runnable system prompt block. Grep for em
dashes returns nothing.

## Documentation requirements
Update tracker and onboarding.

## Done criteria
- [ ] All seven safety boundaries present and explicit
- [ ] A runnable MVP system prompt block present
- [ ] Memory structuring fields named (Person, Category, Memory, Source, Date, Confidence, Sensitivity, Visibility)
- [ ] No em dashes
- [ ] Tracker updated and pushed

## Estimated context size
small

## How to verify completion
`grep -ci "never" RelationshipOS/Assistant_Instructions.md` (expect several) and a manual
read confirming the seven boundaries.
