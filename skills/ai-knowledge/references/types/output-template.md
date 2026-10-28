# Type: output template

The structure an output must follow: a report, a brief, a client email, a ticket, a summary in a fixed format. It is consulted when the assistant produces that output.

## What makes it usable
- When it is used, for which output, and who receives it.
- The fields or sections in order, with what goes in each and which are required.
- Variables marked as `{{field_name}}`, with where their data comes from and what to do when it is missing.
- How strict it is: an exact form to keep, or a default to adapt.

## Diagnosis questions
- Which output does it produce, and is there an approved real one to start from?
- Which parts never change (fixed text, legal lines), and which vary?
- Must the form be kept exactly (a system reads it, a client expects it), or is it a sensible default?
- What happens today when a field has no data? Are there length limits?
- Materials that help: an approved real output, the system or form it goes into, any fixed text that must appear verbatim.

## Typical skeleton
1. When to use it, how strict it is, who receives the output
2. The template, in a fenced block
3. Field notes: for each variable, what it holds, its source, required or not, and what to do when it is missing
4. A filled example with fictional data, when the fields aren't obvious

## Rules for this type
- Name variables by what they hold (`{{client_first_name}}`, not `{{name1}}`); a placeholder without explanation gets filled with plausible inventions.
- State the strictness in the opening line: "Keep this structure and the fixed text exactly", or "Use this as the default structure; drop sections that are empty".
- For each field, choose one rule for missing data: ask for it, leave the line out, or write a fixed fallback.
- Keep instructions out of the template itself, in the field notes, so they aren't copied into the output; keep fixed text verbatim inside it.
- A filled example shows the template exactly, with no field renamed or reordered.

## Sample entry for the plan
The template's first lines in their fenced block, and the field note for one required variable.
