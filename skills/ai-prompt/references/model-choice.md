# Choosing the model and mode

Used for every prompt, for a question about which model or mode to use, and when adjustment rounds keep failing. Models, modes and plans change every few weeks, so a recommendation is only as good as its sources and their date; this file says how to recommend, never which model is best.

## 1. Start from what the user can use
- The candidates are ChatGPT, Claude and Gemini. When the user fixes a vendor, choose only among its models and modes. When they name another assistant, write for it from its official guidance without comparing it to others.
- Recommend among what the user's plan gives them. When it isn't known, ask in the first round, with your guess as the recommended answer. Name an option outside their plan only when it meets a requirement nothing inside it can, and say what getting it costs.

## 2. State the criterion before the options
From the goal, write the two to four requirements that actually separate the options for this prompt: long or many files to read, careful reasoning over figures, browsing for current sources, acting in a browser or an app, writing in a given voice, a fast answer for something run many times. Everything else is a tie. Writing the criterion first keeps the choice from following whichever model is most familiar.

## 3. Consider the mode, not only the model
Inside one app the better choice is often a mode or setting: more reasoning effort, a research mode, an agent mode, a faster model for a template run often, a project or connected source that gives the model the material. Include it when it meets a requirement. When a mode already does part of the prompt's job (asks clarifying questions, shows a plan before running), say so: the prompt can be shorter.

## 4. Research, with sources kept apart
Follow `research.md`. Capabilities, limits, plans and prices come only from official pages, each with its date; independent comparisons say only which option does a requirement better, marked as independent. If the session can't browse, recommend by kind of capability ("the vendor's strongest reasoning model", "a research mode that shows its plan first"), name only models the user already mentioned, and mark every capability, limit and price `[TO CONFIRM]`.

## 5. Give one answer
Recommend one option, with the reason in one line and what it costs: the plan it needs, how long a run takes, usage limits. Show two or three options side by side only when the decision is close or the user asks:

```
Criterion: [requirement 1] · [requirement 2] · …
1. [App, model, mode] — recommended — meets: … · misses: … · costs: … [source, date]
2. [App, model, mode] — meets: … · misses: … · costs: … [source, date]
```

- Never give a name, version, limit or price without a source and a date.
- When the recommended option comes from the same vendor as the model running this skill, say so in the line.
- The user decides. If they keep an option that misses a requirement, say in one line what the result will lack, and adapt the goal's statements so the test judges what the option can do.

## 6. When the target can't reach the result
When adjustment rounds keep failing on the same statement of the goal, say which requirement the target seems unable to meet, and offer two ways out: change the requirement, or move to another model or mode chosen as above.
