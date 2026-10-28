# Chains

Used when the mode is a chain: two or more prompts in which one step's result feeds the next, possibly in different chats, models or modes (a deep research run, then an analysis of the report, then the text for the director). A chain always takes the full path.

## When to propose one
Propose a chain only when the gain can be named in one line:
- a step needs a different model or mode (research, then writing);
- the user must check a result before the next step runs;
- one prompt would ask for too much in a single answer.

Propose it in the plan as a hypothesis, with the single prompt as the alternative, because a chain costs the user copying, pasting and opening chats. The user chooses.

## The map
Each step, in order, with:
- **What it produces,** and its case.
- **Where it runs:** app, model and mode, chosen as `model-choice.md` says, and whether it is a new chat or the same as an earlier step. Default to a new chat when the model or mode changes, or when the earlier discussion would get in the way; keep the same chat when the next step needs the whole discussion. A long chat dilutes instructions; a new chat forces an explicit handover, which can be tested.
- **What passes to the next step:** the whole answer, one section, or an exported file, and where it goes in the next prompt.
- **What the user checks** before running the next step.

A step outside this skill's scope (an image, a video, slides) stays in the map, named, with what it needs to receive; this skill doesn't write its prompt, and the map says which tool or skill takes it.

The Prompt plan holds the map; no step is written before it is approved.

## Writing the steps
- Write every step after the gate, in order.
- Each step's prompt ends by asking for a block made for the next step: the content the next prompt needs, in the format it expects, without the conversation around it. That block is what the user copies.
- Each next prompt marks where that block goes, such as `{step 1 result}`, and says what it is.
- If a real result from one step changes what the next needs, say so, show the change to the map, and ask for approval before continuing.

## Delivering
One block per step, numbered, each with: where to run it, what to paste into it and from where, and what to check before going on.
