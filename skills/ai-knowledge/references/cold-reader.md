# Cold reader

Used in step 2.3. A cold reader checks whether the file works for someone who has only the file, which is exactly the situation of the model in the project. Who runs it, and what to do when the session can't start an agent, is in "Checks by someone who wasn't here" in `SKILL.md`.

## What the reader receives
- The finished file, as it will be attached.
- The neighbor files the triage found overlapping, when there are any, as they are in the project.
- The use cases from the File plan, written as requests, without the expected answers.
- One line on who makes the requests (for example, "a support analyst at a loyalty program"), only if the requests don't make sense without it.
- Never the conversation, the File plan, the source material or the expected answers. Check that the requests don't hint at the answer.

## Prompt
Write it in the user's language and fill in the brackets. Keep the optional lines only when they apply.

```
You are an assistant in a project whose knowledge files are attached: [file name] [Optional: and [neighbor file names]].
[Optional: The requests come from [who].]

Answer each request below using only the attached files. For each one:
1. Your answer, as you would give it.
2. The file and section you used.
3. What you had to guess, or what was missing, unclear or contradictory.

Requests:
1. [use case 1]
2. [use case 2]
3. [use case 3]

Finally:
4. Which terms or rules could you read in more than one way?
[Optional, with neighbor files: 5. Where do the files say the same thing differently, or contradict each other? Which one did you follow?]
[Optional, large project: 6. Pick two sections of [file name] and say whether each would still make sense read alone, without the rest of the file.]

Don't use outside knowledge to fill a gap; say it is a gap.
```

## Using the answers
- Show each answer next to what was expected and propose fixes where they diverge.
- A wrong or guessed answer is a problem of the file, not of the reader: find the missing condition, the rule far from its exception, the term used two ways, the section that depends on another, or the near-duplicate in a neighbor.
- A conflict with a neighbor is resolved by keeping the content in one file and naming that file in the other, with the user's agreement when the neighbor isn't part of this plan.
- Fix only what failed; a gap the material can't fill is asked, never filled with an invented rule.
