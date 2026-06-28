# Relationship OS

Relationship OS is a private, portable, AI-assisted relationship memory system: a modern Rolodex that remembers the context of your real human relationships, not just contact details.

## What it is / what it is not

### What it is

- A structured, user-owned knowledge base for the important people in your life (partner, family, friends, and key professional contacts).
- Plain Markdown files that are the source of truth. They can be opened in any text editor, backed up, version-controlled, or moved anywhere.
- A prompt-engineering framework: you copy a person's profile plus a workflow template into any standard consumer LLM chat window, and the LLM acts as the interface for retrieval, gift planning, date planning, follow-up reminders, conflict preparation, and conversation prep.
- Local-first and zero-surveillance. Nothing runs in the background. The system reads your data only when you manually paste it into an LLM.

### What it is not

- It is not a dating app.
- It is not a therapy, counseling, or mental-health platform.
- It is not a medical, fertility, or health advisor.
- It is not a period tracker.
- It is not a sales CRM, and it is not a proprietary database that locks your data into a closed platform.

## Folder map

```
RelationshipOS/
  README.md            This file: positioning and how to use the system.
  Relationships/       One Markdown profile per person (filled in later phases).
  Templates/           Reusable profile and workflow prompt templates.
  Logs/                Append-only memory logs that record what changed and when.
```

- `Relationships/` holds an individual profile file for each person you track.
- `Templates/` holds the profile template plus the workflow prompts (gift planning, date planning, conflict prep, memory updates, and retrieval) and the supporting privacy model and data schema.
- `Logs/` holds the source-tagged memory update log so every saved detail has a record of where it came from and when.

## How to use

The system has no application to install and no service to run. You use it with any standard consumer LLM:

1. Open the `RelationshipOS/` folder in any text editor.
2. Copy the relevant person's profile from `Relationships/` (or start a new one from the profile template in `Templates/`).
3. Copy a workflow template from `Templates/` (for example, the gift planner or the date planner).
4. Paste both the profile and the workflow template into any standard consumer LLM chat window, then ask your question.
5. When the LLM helps you capture a new detail, paste the update back into the person's profile and record it in the memory log under `Logs/`.

Because plain Markdown is the source of truth, you stay in full control of your data. You can edit it by hand at any time, keep it entirely offline, and use whichever LLM you prefer. If a profile or log grows large enough to strain an LLM context window, archive older log rows under a historical heading inside the same file so the active section stays small.
