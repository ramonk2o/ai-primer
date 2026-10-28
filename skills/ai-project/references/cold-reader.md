# Cold reader

Used in the Test step. The cold reader shows whether the instructions send each request to the right source and whether the sources answer it, for a reader who has only what the project will have. Who reads, and what to do when the session can't start an agent, is in "Tested by someone who wasn't here" in `SKILL.md`.

## What the reader receives

- The instructions for one destination, as they will be pasted. With more than one destination, use the one with the most users; the versions share their logic.
- The knowledge files, as they will be attached, with their names.
- For each live source, its description only. The reader can't fetch it, so it reports what it would fetch and when; the fetch itself is tested on the platform.
- The use cases from the Project plan, written as requests, without the expected answers. They must not name the file to use or hint at the answer.
- Never the conversation, the Project plan or the source material.

## Prompt

Write it in the user's language and fill in the brackets.

```
You are the assistant in a project. Its instructions are below, and its files are attached: [file names]. [It also reaches these sources through tools you don't have here: (descriptions). When a request needs one, say what you would fetch instead of answering from it.]

<instructions>
[instructions text]
</instructions>

Answer each request as the project's assistant, using only the instructions and the files. For each one:
1. Which file or source you would use, and what in the instructions sent you there.
2. Your answer, as you would give it.
3. What you had to guess, or what was missing, unclear or contradictory.

Requests:
1. [use case 1]
2. [use case 2]
3. [use case 3]

Finally:
4. Is there a request this project is clearly meant for that the instructions don't tell you how to handle?
5. Did you find a rule stated in two places, or two rules that contradict each other?

Don't use outside knowledge to fill a gap; say it is a gap.
```

## Reading the answers

- The wrong file or none: the instructions are at fault. Make the trigger an intent the request actually expresses, or name the file more descriptively.
- The right file but a wrong or guessed answer: the file is at fault. Find the missing condition, the rule far from its exception, or the section that depends on another.
- A duplicated or contradictory rule: keep it in one place; the instructions hold only what must apply in every chat.
- Then apply "Fixes" in `SKILL.md`: what changes no decision goes straight, and what adds or changes a rule, a fact, a file or a source goes to the user as a written proposal.
