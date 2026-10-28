# Diagnosis and adjustment rounds

Used in diagnosis mode, when the user brings a prompt and a result that came out wrong, and when the user brings back what a real run of a delivered prompt produced. Both follow the same method: compare the result with what was wanted, name the likely cause, and change one thing at a time.

## Diagnosis mode
- Ask in one line for whichever is missing: the prompt, the result, or where it ran (app, model, mode, and whether inside a project). A description of the result works when there is no copy.
- Settle what the right result would have been. A wrong result often comes from a goal that was never settled, so check that first, as "What the user wants" in `SKILL.md` says, before blaming the wording.
- Name the likely cause: an open decision the model filled in, missing context, two rules in conflict, a format described loosely, the wrong model or mode for the job, or a trick that works against the current model.
- The diagnosis and the change go into the Prompt plan, and the revised prompt is its draft.
- Change one thing at a time, the one most likely to fix it, and name any other cause for the next round. When two changes only work together, make them one step and say so.
- A fix to one prompt takes the light path; a fix that changes the goal, the target or several prompts of a chain takes the full path.

## Adjustment rounds
- When the user brings back what the real run produced, compare it with the goal's statements and name what differs.
- Propose one change at a time with its reason, as in diagnosis mode.
- A change to the goal or the target goes back to the plan.
