# Phase 4 - Privacy Model and Data Schema - Start Brief

## Objective
`RelationshipOS/Templates/Privacy_Visibility_Model.md` documents the privacy and visibility
model, and `RelationshipOS/Templates/Data_Model_Schema.md` documents the future-app schema,
both as plain Markdown with no executable code.

## Scope
In scope: the privacy/visibility model document and the data-model schema document. Out of
scope: workflows and the example profile.

## What already exists
Phases 1 to 3 produced the tree, README, Assistant_Instructions, Profile_Template, and the
memory log.

## What to inspect first
- `RelationshipOS/Logs/Memory_Update_Log.md` (visibility and sensitivity enums must match)
- `RelationshipOS/Templates/Profile_Template.md` (category names feed the schema Category enum)

## Files likely to be created or edited
- `RelationshipOS/Templates/Privacy_Visibility_Model.md`
- `RelationshipOS/Templates/Data_Model_Schema.md`

## What must NOT change
The log column order and the profile section order.

## Install or deployment impact
None.

## Testing requirements
Privacy_Visibility_Model.md must define visibility values (Private, Shared, Suggested,
Archived) and sensitivity values (Normal, Sensitive, Highly Sensitive), partner-controlled
sharing, and opt-in wellness/cycle context framed respectfully as shared wellness (never
tracking or monitoring). Data_Model_Schema.md must define, as Markdown tables, the fields,
types, and enums for: Person, Memory, Category, Visibility, Sensitivity, Source. Enums must
match those used in the memory log. No SQL, TypeScript, or other code. Grep for em dashes
returns nothing.

## Documentation requirements
Update tracker and onboarding.

## Done criteria
- [ ] Privacy model defines visibility + sensitivity + partner sharing + shared wellness
- [ ] Schema defines all six entities with fields, types, enums, as tables only
- [ ] Enums consistent with the memory log
- [ ] No code, no em dashes
- [ ] Tracker updated and pushed

## Estimated context size
small

## How to verify completion
`grep -niE "private|shared|suggested|archived" RelationshipOS/Templates/Privacy_Visibility_Model.md`
and a read confirming all six schema tables exist.
