# Data Model Schema

This document describes the data model that a future Relationship OS application could be
built on. It is documentation only. The MVP ships as plain Markdown files, and this schema
records, in plain language and Markdown tables, the entities, fields, types, and enumerated
values those files already express. Nothing here is executable, and building an app is out of
scope for this phase.

The model has six entities. Two are data entities, Person and Memory. Four are enumerated
value sets that the Memory entity refers to: Category, Visibility, Sensitivity, and Source.
The enumerated values match those used in `Logs/Memory_Update_Log.md`, and the Category names
match the categories used across `Templates/Profile_Template.md`. The eight Memory fields
match the eight columns of the memory log and the eight fields defined in
`Assistant_Instructions.md`, and they must stay aligned across all of them.

The Type column uses plain descriptive types rather than any specific database or programming
type. "Identifier" means a unique key, "Text" means free-form text, "Date" means a calendar
date written as YYYY-MM-DD, and "Enum (Name)" means a value drawn from the named enumerated
set defined later in this document.

## Person

One record per person you track. The fields mirror the Basic Information and supporting
sections of `Templates/Profile_Template.md`.

| Field | Type | Required | Notes |
|-------|------|----------|-------|
| person_id | Identifier | Yes | Unique key for the person. |
| full_name | Text | Yes | The person's full name. |
| preferred_name | Text | No | Preferred name or nickname. |
| relationship_to_me | Text | No | For example partner, parent, sibling, close friend, colleague. |
| pronouns | Text | No | The person's pronouns. |
| location | Text | No | City and region. |
| how_we_met | Text | No | Short note on how the relationship began. |
| known_since | Text | No | Roughly how long you have known each other. |
| best_contact_method | Text | No | Preferred channel: call, text, email, or in person. |
| default_visibility | Enum (Visibility) | No | Default Visibility for new memories about this person, set in the profile AI Instructions. |
| notes | Text | No | Free-form profile context that does not belong to a single memory. |

## Memory

One record per saved detail about a person. These are the eight fields used throughout
Relationship OS. Each Memory belongs to exactly one Person and carries its own provenance and
privacy controls.

| Field | Type | Required | Notes |
|-------|------|----------|-------|
| person | Identifier (references Person) | Yes | Who the memory is about. |
| category | Enum (Category) | Yes | The type of memory. |
| memory | Text | Yes | The specific detail, written plainly. |
| source | Enum (Source) | Yes | Where the detail came from. Free text, never guessed. See the Source entity. |
| date | Date | Yes | The date the memory was recorded or the date the detail refers to, in YYYY-MM-DD form. |
| confidence | Enum value: High, Medium, or Low | Yes | How certain the detail is. |
| sensitivity | Enum (Sensitivity) | Yes | How private the detail is. |
| visibility | Enum (Visibility) | Yes | Who the detail may be referenced around. |

## Category

The enumerated set of memory types. These names match the categories used across
`Templates/Profile_Template.md` and the Category examples in `Logs/Memory_Update_Log.md`.

| Value | Meaning |
|-------|---------|
| Preference | Something the person tends to enjoy or favor. |
| Important Date | A birthday, anniversary, milestone, or other date worth remembering. |
| Family | A family member or close person and their role. |
| Health and Wellness | Non-clinical lifestyle context such as dietary preferences, energy patterns, and comfort needs. |
| Work | The person's job, projects, or professional context. |
| Conflict | A tension, disagreement, or delicate matter to handle with care. |
| Gift Idea | A gift candidate or signal for this person. |
| Shared History | A shared memory, inside joke, or ongoing thread between you and the person. |

## Visibility

The enumerated set that decides where a detail may be referenced. These four values match the
Visibility column in `Logs/Memory_Update_Log.md` and the values defined in
`Templates/Privacy_Visibility_Model.md`.

| Value | Meaning |
|-------|---------|
| Private | For your eyes only; never referenced around or to anyone else. |
| Shared | May be referenced openly within the relevant relationship context. |
| Suggested | The assistant may proactively surface or suggest this detail when relevant. |
| Archived | Retained for the record but inactive; not surfaced in normal use. |

## Sensitivity

The enumerated set that rates how private a detail is. These three values match the
Sensitivity column in `Logs/Memory_Update_Log.md` and the values defined in
`Templates/Privacy_Visibility_Model.md`.

| Value | Meaning |
|-------|---------|
| Normal | Everyday context that is not particularly private. |
| Sensitive | Personal details that deserve discretion and are kept out of casual suggestions. |
| Highly Sensitive | The most private details; isolated, never raised unprompted, used only as explicitly directed. |

## Source

Where a detail came from. In `Logs/Memory_Update_Log.md`, Source is free text and is never
guessed, so the Source entity stores a free-text value. The values below are the common
source phrases the log uses; they are suggestions for consistency, not a closed list, and you
may record any accurate free-text source.

| Field | Type | Required | Notes |
|-------|------|----------|-------|
| value | Text | Yes | The free-text source of the detail. Never guessed. |

Common values used in the memory log:

| Value | Meaning |
|-------|---------|
| told me directly | The person stated the detail to you. |
| observed | You noticed the detail yourself. |
| inferred from conversation | You reasoned the detail from something said, with lower certainty. |
| third party | Someone other than the person told you. |

## How the entities relate

A Person has many Memory records, and each Memory belongs to exactly one Person through the
person field. Each Memory draws its category, source, sensitivity, and visibility from the
matching enumerated set, and its confidence from the High, Medium, or Low values. This is the
same shape as one row in `Logs/Memory_Update_Log.md`: a single Memory record is a single log
row, tagged with its Person, its provenance, and its privacy controls.
