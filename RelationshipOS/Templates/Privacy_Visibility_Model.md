# Privacy and Visibility Model

This document defines how Relationship OS treats the privacy of the details you store about
the people in your life. It explains the two controls that travel with every memory,
Sensitivity and Visibility, how partner-controlled sharing works, and how optional shared
wellness context is handled with respect.

Relationship OS is local-first and user-owned. Plain Markdown files are the source of truth,
nothing runs in the background, and the system reads your data only when you choose to paste
it into an LLM. Privacy here is a discipline you apply to your own files, and the assistant is
built to honor it.

Every memory carries two privacy controls: a Sensitivity value (how private the detail is)
and a Visibility value (who the detail may be referenced around). These two values are
independent. Sensitivity describes the nature of the detail; Visibility describes where it may
surface. The same names are used in `Logs/Memory_Update_Log.md` and in
`Templates/Data_Model_Schema.md`, and they must stay aligned across all three.

## Sensitivity

Sensitivity rates how private a detail is. Every memory is assigned exactly one of the three
values below. The assistant flags Sensitive and Highly Sensitive details, keeps them out of
casual suggestions, and never uses them lightly.

- **Normal:** everyday context that is not particularly private. Most preferences, hobbies,
  and general notes fall here. The assistant may use these freely within whatever the
  Visibility value allows.
- **Sensitive:** personal details that deserve discretion, such as money matters, family
  tensions, or anything the person would not want shared loosely. The assistant handles these
  carefully and keeps them out of casual or unrelated suggestions.
- **Highly Sensitive:** the most private details, such as deeply personal struggles or things
  shared in confidence. The assistant isolates these, never raises them on its own, and uses
  them only when you explicitly direct it to and only within the bounds of their Visibility.

Sensitivity is a property of the detail and does not by itself decide who may hear it. That is
the job of Visibility.

## Visibility

Visibility decides where a detail may be referenced. Every memory is assigned exactly one of
the four values below. These four values are the same set used by the Visibility column in
`Logs/Memory_Update_Log.md`.

- **Private:** for your eyes only. The assistant may use the detail to help you privately but
  never references it around or to anyone else, including the person it is about.
- **Shared:** the detail may be referenced openly in the relevant relationship context, for
  example with a partner in a shared household or among people who already know it. Shared
  does not mean public; it means the detail is not a secret within its natural circle.
- **Suggested:** the assistant may proactively surface or suggest this detail when it is
  relevant, for example raising a gift idea before a birthday or reminding you of an open
  thread. Suggested invites the assistant to bring the detail to your attention without
  waiting to be asked.
- **Archived:** the detail is retained for the record but is inactive. The assistant does not
  surface it in normal use and treats it as historical context that stays out of current
  suggestions until you reactivate it.

You set a default Visibility per person in the AI Instructions section of that person's
profile, and you can override Visibility on any individual memory.

## How Sensitivity and Visibility work together

Sensitivity and Visibility are evaluated together for every memory. Visibility sets the
outer limit of where a detail may appear, and Sensitivity tightens how carefully the
assistant handles it within that limit. A Highly Sensitive detail marked Shared is still
handled with care and is never dropped into a casual suggestion, even though its Visibility
would otherwise allow it to be referenced in context. When the two values are in tension, the
more protective reading wins.

## Partner-controlled sharing

Partner-controlled sharing governs what happens when two partners each keep their own
Relationship OS files and want some context to be visible to each other.

- **You own your files.** Each partner is the sole owner of their own Markdown profiles and
  logs. Nothing crosses from one partner's files to the other automatically. Sharing happens
  only when a file owner chooses to share, by giving the other partner a copy of the specific
  details marked Shared.
- **The owner of a memory controls its sharing.** Whether a detail may reach a partner is
  decided by the Visibility you set on that detail. Details marked Private stay with you and
  are never surfaced to a partner. Details marked Shared are the ones eligible to be shared
  with a partner in your shared context.
- **Sharing is per detail, not all or nothing.** Because Visibility is set on each memory, you
  can share some context while keeping other context private, within the same person's
  profile.
- **Sharing is revocable.** Visibility can be changed at any time. Moving a detail from Shared
  to Private or Archived removes it from what the assistant will reference in a shared
  context going forward.

The result is that each partner stays in full control of their own relationship knowledge,
and the assistant only ever treats a detail as shareable when its owner has marked it Shared.

## Opt-in shared wellness context

Relationship OS includes an optional, opt-in place to record non-clinical shared wellness
context about a partner, such as comfort needs, energy patterns, dietary preferences, and the
rhythms of their week or month, including cycle-related context a partner chooses to record.
The single purpose is to help you be more considerate: to plan a gentle evening, choose a
meal that sits well, time a thoughtful gesture, or simply show up with more care.

This feature is built around respect, consent, and partner control:

- **It is opt-in and partner-controlled.** Nothing in this area is recorded unless the partner
  agrees to share it, and the partner decides what goes in and what stays out. They can ask
  for any entry to be removed at any time.
- **It is shared wellness, framed with care.** Entries are kept in the partner's voice as
  context they have chosen to share so you can be supportive. They are not collected behind a
  partner's back and are not used to draw conclusions about them.
- **It is non-clinical only.** No diagnoses, symptoms, medications, or clinical interpretation
  belong here. Cycle-related context is recorded only as general rhythm a partner shares to
  help you plan considerately, never as a medical record and never to predict or analyze.
- **It honors Sensitivity and Visibility.** Wellness context is usually Sensitive or Highly
  Sensitive and is given a Visibility that matches what the partner is comfortable with. The
  assistant handles it under the same protections as every other memory.
- **The boundaries still apply.** The assistant never diagnoses, never gives medical,
  therapeutic, or fertility advice, and never treats this context as anything more than a way
  to help you care for someone well. Relationship OS is not a medical tool, a fertility tool,
  or a period tracker, and this feature does not change that.

If a partner is ever uncomfortable, the right move is the same one the assistant recommends
whenever a relationship situation is uncertain: talk with them directly, and let their wishes
set the Visibility.
