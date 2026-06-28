# Memory Update Log

This is the source-tagged ledger for every detail you save about the people in
`Relationships/`. When the assistant proposes a new memory and you confirm it, append one row
here so the detail is never stored without provenance. The eight columns match the eight
memory fields defined in `Assistant_Instructions.md`: Person, Category, Memory, Source, Date,
Confidence, Sensitivity, Visibility.

## How to use this log

- Append a new row every time you save or update a memory; do not overwrite history.
- Source is free text and is never guessed (for example "told me directly", "observed",
  "inferred from conversation", "third party").
- Date is the date the memory was recorded or the date the detail refers to, in YYYY-MM-DD
  form.

## Column guidance

- **Person:** who the memory is about.
- **Category:** the type of memory (for example Preference, Important Date, Family, Health and
  Wellness, Work, Conflict, Gift Idea, Shared History).
- **Memory:** the specific detail, written plainly.
- **Source:** where the detail came from. Free text, never guessed.
- **Date:** YYYY-MM-DD.
- **Confidence:** how certain the detail is. One of High, Medium, Low.
- **Sensitivity:** how private the detail is. One of Normal, Sensitive, Highly Sensitive.
- **Visibility:** who the detail may be referenced around. One of Private, Shared, Suggested,
  Archived.

## Log

| Person | Category | Memory | Source | Date | Confidence | Sensitivity | Visibility |
|--------|----------|--------|--------|------|------------|-------------|------------|
| Maya Reyes | Preference | Loves dark chocolate, dislikes milk chocolate | told me directly | 2026-06-20 | High | Normal | Shared |
| Maya Reyes | Important Date | Birthday is March 14 | told me directly | 2026-06-20 | High | Normal | Shared |
| Maya Reyes | Gift Idea | Wants new Altra trail running shoes, US 8 womens, wide toe box | told me directly | 2026-06-21 | High | Normal | Suggested |
| Maya Reyes | Health and Wellness | Mostly vegetarian, eats fish occasionally, prefers lighter evening meals | told me directly | 2026-06-21 | High | Normal | Shared |
| Maya Reyes | Shared History | First date was a tide pool walk at Cannon Beach | observed | 2026-06-21 | High | Normal | Shared |
| Maya Reyes | Important Date | Mid-November anniversary of her grandmother's passing; keep the day quiet | told me directly | 2026-06-21 | High | Sensitive | Private |
| Maya Reyes | Work | Weighing a bigger role at work; keep private until she decides | told me directly | 2026-06-22 | Medium | Sensitive | Private |
