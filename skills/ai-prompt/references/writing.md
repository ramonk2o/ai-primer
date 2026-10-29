# Writing the prompt

Used in the Write step and for the light path's draft. These rules apply to every case; the case file adds what its kind of prompt needs, and the target's current guidance wins where it says something different.

## Lead with the result
- Open with what the prompt must produce and what it is for. Current models plan their own path, so steps are written only when the process itself matters (the sources to check first, the order of a deliverable, the action an agent must never take).
- Give the context the target needs and can't know: who the result is for, where it will be used, what has been tried, what the user already knows.
- Say what a good result must have, from the plan's statements, in words the target can act on. For a text result that is often the last part: the format, the evidence required, the length.

## Fit where it lands
- In a project with instructions, the prompt adds only what this request needs; it doesn't repeat or contradict the project's rules, and it names a project file when the request depends on it.
- In a new chat, the prompt carries all the context; attached files are named and said what to use them for.
- In a chain step, it names where the previous step's result goes, as `chain.md` says.

## Make the open decisions visible
- Every decision the plan settled is stated as the user's choice, once.
- Every decision the plan left to the model is stated as the model's call, with a request to say how it decided, so the user can check it.
- A prompt that leaves a decision implicit gets a different answer each run.

## Say each thing once
- One instruction, one place. A rule repeated in three phrasings gets weighed three times, and two rules that pull against each other make the model spend its effort reconciling them; the plan decides which wins and the prompt states only that one.
- Give the reason for a rule that isn't obvious, in a short clause ("plain text, because it goes into a form"); a model generalizes from a reason and applies a bare rule rigidly.
- No capitals, "CRITICAL" or "IMPORTANT" for emphasis: they make a model apply the rule out of context.

## Say what you want
- Phrase instructions as what to do ("write in short paragraphs") rather than what to avoid.
- Concrete beats adjectival: "for a director who reads it on the phone between meetings" says more than "concise and professional".

## Ask for the expert's work, not the expert
- Name the methods, tools, sources and material a leading professional would use for this task, from the plan's "Methods and material" line, instead of a role ("you are a senior analyst"). A role changes the answer's vocabulary without changing how the work is done.
- When the target can check its result against something outside it (running a calculation, cross-checking sources, comparing with a file), ask for that check and its evidence next to the result. A model asked only whether its work is right tends to say yes.

## Structure
- Separate the parts of a prompt that mixes instructions, context, examples and inputs, with headings or tags (`<context>`, `<input>`), named the same way throughout.
- Long material goes before the request, and the request at the end.

## Examples
- Use examples only when they show what words can't: a format, a tone, a borderline case. For a reasoning mode, start without them and add them only if the result needs them.
- Three to five, varied, close to the real inputs; similar examples get copied, including their accidents.
- Each behavior shown in an example is also stated as a rule, because an example alone is a hint.

## What stays out
- Instructions to reason step by step for a mode that reasons on its own; they can make results worse.
- App settings (the mode, files to attach): they go in the delivery's settings list.
- The conversation, the plan's labels and any note to the user.
- Placeholders are written so they can't be missed: `[placeholder: client's name]` in a one-off prompt, `{variable}` in a template.

## Length
The plan's shape sets the approximate length. A prompt that comes out much longer than planned usually repeats itself or carries a decision the plan didn't make; cut it, or go back to the plan. Short is fine: inside a project whose instructions carry the work, a good prompt can be a few lines.
