# Phase 3 - Profile Template and Memory Log - Start Brief

## Objective
`RelationshipOS/Templates/Profile_Template.md` contains all 11 sections in the exact
required order, and `RelationshipOS/Logs/Memory_Update_Log.md` implements the 8-column
source-tagged table in the exact required order.

## Scope
In scope: the profile template and the memory log. Out of scope: the privacy model, the
schema, the workflows, the example profile.

## What already exists
Phases 1 and 2 produced the tree, README, and Assistant_Instructions.

## What to inspect first
- `RelationshipOS/Assistant_Instructions.md` (the memory field names must match the log columns)

## Files likely to be created or edited
- `RelationshipOS/Templates/Profile_Template.md`
- `RelationshipOS/Logs/Memory_Update_Log.md`

## What must NOT change
The assistant instructions and README.

## Install or deployment impact
None.

## Testing requirements
Profile_Template.md must contain these 11 level-2 headers in this exact order:
Basic Information; Preferences; Dislikes; Gift Ideas; Communication Style; Relationship
Notes; Goals; Health and Wellness; Dates and Events; Boundaries; AI Instructions.
Memory_Update_Log.md must be a Markdown table with these 8 columns in this exact order:
Person; Category; Memory; Source; Date; Confidence; Sensitivity; Visibility. The Health
and Wellness section must be strictly non-clinical (dietary preferences, energy levels),
never diagnostic. Grep for em dashes returns nothing.

## Documentation requirements
Update tracker and onboarding.

## Done criteria
- [ ] 11 sections present in exact order
- [ ] 8-column log table in exact order with enum guidance (Confidence High/Medium/Low; Sensitivity Normal/Sensitive/Highly Sensitive; Visibility Private/Shared/Suggested/Archived)
- [ ] Health and Wellness section is non-clinical
- [ ] No em dashes
- [ ] Tracker updated and pushed

## Estimated context size
small

## How to verify completion
`grep -nE "^## " RelationshipOS/Templates/Profile_Template.md` shows the 11 headers in
order; the log header row lists the 8 columns.
