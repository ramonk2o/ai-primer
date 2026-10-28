# Cold executor and judge

Used in the Test step. A prompt is judged by what it produces, so an executor who has only the prompt runs it, and a judge who has only the result and the goal's statements says whether it meets them. They are separate because a producer grading its own result reads it charitably. Who runs them is in "Tested by someone who wasn't here" in `SKILL.md`. The executor is not the target model, so the test checks the prompt, not the target; say so in the delivery.

## What each one receives
- **Executor:** the prompt exactly as it will run, with real inputs in its slots, plus what the target would also have: the project instructions when the prompt lands in a project, the files it will attach, one line on what an agent can reach. Never the conversation, the Prompt plan, the goal's statements or what the prompt is meant to achieve.
- **Judge:** the executor's result, the input it was given, and the goal's statements from the Prompt plan. Never the conversation or the prompt's history.

## What the executor does, by case
- **One-off ask:** answers it.
- **Conversation opener:** writes only the first reply, as the assistant would.
- **Template:** runs the prompt once per input — two or three of the user's real inputs, including an odd one. Inputs you made up, when the user had none, are labeled synthetic.
- **Deep research:** doesn't research. It writes the research plan it would follow and the outline of the report, and says what it would have to guess.
- **Agent task:** doesn't act. It describes step by step what it would do, where it would ask before going on, when it would stop, and what it would report.
- **Chain:** runs the text steps in order, each with the previous step's result in its slot — the user's real one if they have it, otherwise the executor's own — so no expectation of yours reaches it. The judge checks the final result and each check point in the map.

## Executor prompt
Write it in the language of the prompt under test and fill in the brackets.

```
Below is a prompt as it will be given to an AI assistant. Treat it as given to you, with one limit: don't take any action or use any tool that acts outside this conversation, even if the prompt asks you to.
[Project:] It runs inside a project with these instructions: <instructions>…</instructions>
[Conversation opener:] Write only your first reply.
[Deep research:] Don't research. Write the research plan you would follow and the outline of the report you would deliver.
[Agent task:] You will have access to [what the agent can reach]. Don't act and don't use tools. Describe step by step what you would do, where you would ask before continuing, when you would stop, and what you would report.

Then, separately, under "Notes":
1. What did you have to guess or assume?
2. Which instructions could you read in more than one way, or seemed to conflict?

[prompt with inputs]
```

## Judge prompt

```
Below are a result produced by an AI assistant, the input it received, and statements a good result must meet.
For each statement, answer yes or no, and quote the part of the result that decides it.
Then say what in the result would bother the person who will use it, if anything.
Judge only from the result; don't guess what was meant.

Input: [input]
Statements:
1. [statement 1]
2. …
Result: [executor's result]
```

## Without an agent
The user pastes the executor's prompt into a new conversation and brings the answer back. Then judge it here, statement by statement, quoting the result for each verdict, and say in the delivery that the judge wasn't independent.

## Using the answers
- A "no" from the judge is a problem of the prompt: find the missing instruction, the rule that conflicts with another, or the context the executor didn't have, and propose a fix.
- The executor's notes point to ambiguities; fix the ones that touch a statement of the goal.
- For an agent task, any step that would act without confirmation where the plan asks for it, or keep going where it should stop, is a failure even if the rest is right.
- Show the findings next to the statements. A fix that adds or changes a rule, a fact or what the prompt asks is a proposal the user approves; a fix that changes no decision goes straight.
