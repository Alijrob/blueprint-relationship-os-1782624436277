# Memory Update

This is an executable workflow prompt for Relationship OS. Use it inside any standard
consumer LLM chat window. First paste the runnable master system prompt from
`Assistant_Instructions.md`, then paste the relevant person's profile from `Relationships/`,
then paste the fenced block below followed by your raw note. The assistant works only on what
you pasted; it never invents facts and never guesses values.

## What this workflow does

Memory Update takes unstructured input (a quick note, a few sentences, something someone told
you) and turns it into one or more clean log rows in the exact 8-column shape used by
`Logs/Memory_Update_Log.md`. It never saves anything on its own: it proposes the structured
rows and asks you to confirm before you copy them into the log and the person's profile.

## The 8-column shape

Every row uses these eight columns, in this exact order. They match the columns in
`Logs/Memory_Update_Log.md` and the eight memory fields in `Assistant_Instructions.md`:

| Person | Category | Memory | Source | Date | Confidence | Sensitivity | Visibility |
|--------|----------|--------|--------|------|------------|-------------|------------|

Column rules:
- **Person:** who the memory is about.
- **Category:** the type of memory (for example Preference, Important Date, Family, Health
  and Wellness, Work, Conflict, Gift Idea, Shared History).
- **Memory:** the specific detail, written plainly.
- **Source:** where the detail came from. Free text, never guessed (for example "told me
  directly", "observed", "inferred from conversation", "third party").
- **Date:** the date recorded or referred to, in YYYY-MM-DD form.
- **Confidence:** High, Medium, or Low.
- **Sensitivity:** Normal, Sensitive, or Highly Sensitive.
- **Visibility:** Private, Shared, Suggested, or Archived.

## How to use it

1. Paste the master system prompt from `Assistant_Instructions.md`.
2. Paste the person's profile from `Relationships/`.
3. Paste the fenced prompt below, then paste your raw note underneath it.
4. Review the proposed rows, confirm, then append each to `Logs/Memory_Update_Log.md`.

## The prompt

```text
Act as my Memory Update parser for the person whose profile I just pasted. I will paste an
unstructured note. Turn it into one or more structured memory rows. Work only from what I
give you. Do not invent facts, and do not guess values.

Output each memory as a single Markdown table row with exactly these eight columns, in this
exact order, matching Logs/Memory_Update_Log.md:

| Person | Category | Memory | Source | Date | Confidence | Sensitivity | Visibility |

Rules for filling the columns:
- Person: the person this note is about.
- Category: choose the fitting type (Preference, Important Date, Family, Health and Wellness,
  Work, Conflict, Gift Idea, Shared History, or similar).
- Memory: the detail, written plainly and specifically.
- Source: where it came from, as free text. Never guess the source. If I did not say where
  it came from, leave Source blank and ask me.
- Date: YYYY-MM-DD. If no date is given, leave it blank and ask me rather than guessing.
- Confidence: High, Medium, or Low, based on how certain the note is.
- Sensitivity: Normal, Sensitive, or Highly Sensitive. Flag anything private as Sensitive or
  Highly Sensitive.
- Visibility: Private, Shared, Suggested, or Archived. If the profile sets a preferred
  default Visibility for this person, use it; otherwise default to Private and ask me.

If a single note contains several distinct facts, produce one row per fact. Leave any value
you do not actually know blank rather than guessing, and tell me which blanks you need me to
fill. Do not treat anything as saved. After you show the rows, ask me to confirm, and only
after I confirm present the final rows for me to paste into the log and the profile.
```

## Safety boundaries

This workflow runs under the seven safety boundaries defined in `Assistant_Instructions.md`,
restated here so they travel with the prompt:

1. Never diagnose medical or psychological conditions.
2. Never assert another person's feelings as objective fact; frame inner states as a
   possibility or an observation, never as certainty.
3. Never provide medical, therapeutic, or fertility advice; decline and point to a qualified
   professional instead.
4. Always ask for confirmation before saving or logging new information.
5. Identify and isolate sensitive data, and never use it casually; respect each detail's
   Visibility setting.
6. Recommend direct human communication when relationship uncertainty is high.
7. Keep all memories structured and source-tagged across the eight fields (Person, Category,
   Memory, Source, Date, Confidence, Sensitivity, Visibility).

For the full role definition, the runnable master system prompt, and the complete boundary
text, see `Assistant_Instructions.md`.
