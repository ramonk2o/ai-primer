# Case: conversation opener

A prompt that opens multi-turn work: designing something together, working through an analysis in rounds, preparing a presentation, thinking a problem through. What it produces is not one answer but how the conversation goes, so a good prompt sets the goal, the way of working and what must not happen yet, and leaves the content to the turns.

## What a good result needs
- A first reply that does the right first thing: reads what it was given, asks what it must ask, proposes before asking, and doesn't jump to the final deliverable.
- A way of working the user would have chosen: rounds of questions, a plan before acting, drafts shown before changes, when to stop and ask.
- The goal and its limits held across turns, without the user repeating them.

## Where it lands
- **A project with instructions:** the instructions already say how the assistant works there. Read them when the user has them; the prompt brings only this conversation's goal, materials and anything that differs, and never restates the project's rules.
- **A new chat:** the prompt carries the context and the way of working, briefly; if the same opener will be used again and again, that is a sign the work needs a project (ai-project).

## Materials that help
The project instructions, if any; what the user will bring to the conversation (files, links, an earlier draft); an earlier conversation that went well or badly.

## Diagnosis questions
- What should exist, or be decided, when the conversation ends?
- What should the first reply do, and what should it not do yet?
- How does the user want to be consulted: questions in rounds, a plan to approve, drafts to react to?
- What must the assistant read or check before proposing anything?
- What would make the user abandon the conversation halfway?

## Writing the prompt
- **The goal of the conversation,** and what "done" means for it.
- **What to read first:** the files, links or sources, and what to look for in each.
- **The first move,** stated once ("start by reading X and bring a round of questions; don't edit anything yet").
- **The way of working** only where it differs from the project's instructions or the model's default.
- **What the user is unsure about,** said plainly, so the assistant helps think it through instead of assuming.

## Typical shape
The goal in one or two sentences; the materials and what to do with them; the first move; any way-of-working rule that isn't already in the project. Often a short paragraph or a few lines.

## Pitfalls
- Restating the project's instructions, so two versions of the same rule compete.
- Asking for the final deliverable in the opener, so the first reply skips the thinking.
- No first move, so the reply is a generic plan or a list of questions with no proposals.
- A goal stated as a topic ("the new skill") where a result belongs ("a plan for the skill I can approve").
