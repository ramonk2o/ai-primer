# metawork principles

metawork's skills help people write what LLMs read: prompts, project instructions and knowledge files. Each skill settles with the user what a good result is before writing, and tests the result outside the conversation. This file holds the principles every skill follows and the questions for judging a change. A change that breaks a principle is a design decision and needs the maintainer's explicit agreement.

## Taking a request

1. **One skill per request; steps can be handed over.** Each skill states at the start of its `SKILL.md` the requests it leaves out and which sibling covers them, so two skills never offer themselves for the same request; a request no skill fits is handled without the plugin. During the work, when a sibling the session can load does a step better, the skill hands that step over and takes the result back; the sibling starts without its offer and treats what was approved as settled. When no sibling is available, the skill does the step itself.
2. **Offer before taking over, unless the draft costs less.** A skill started by the subject of a request, not by its name, first offers itself in one short message: what it does differently, what it costs, and a recommended answer. When the output is a few lines, such as an image prompt or a short prompt, the first reply is the draft, with one line on what the skill adds. If the user declines, the request is handled without the skill, which isn't offered again in that conversation.
3. **The request is a hypothesis.** A request names an output but answers a situation. When something shows the output won't solve it (a prompt where the case needs a project, a knowledge file where a few lines of instructions would do), the skill says so in the first round, with what would, and follows the user's answer. When nothing points to a mismatch, it doesn't ask.

## Planning with the user

4. **Depth matches the stakes.** Output that runs unattended, runs often or shapes every chat in a project gets the full flow. Small or one-off output gets a light path, and every addition to a flow states whether it applies there.
5. **Propose before asking.** Each message brings a round of up to five numbered questions, each with the recommended answer and a one-line reason, ordered by risk; a question whose answer changes the others goes first, and its dependents wait. When the material answers a question, the skill uses that answer and says where it came from. Missing material never blocks: the skill drafts, hypothesizes and says where the information might be.
6. **Nothing invented.** Facts about the user's world come from the material or the user, and one only they can know is never guessed in a recommended answer; it stays `[TO CONFIRM]`. Facts about a tool (features, parameters, limits, syntax) come from its current official documentation, never from the model's memory. A gap in a knowledge file is marked, not filled.
7. **One plan, approved explicitly, on real text.** The plan carries a sample of the output (a section of the instructions, a passage of the file, the whole prompt when it is short), so the user judges text, not a description of it. "OK" or "go ahead" approve it; silence, a passing comment or approving a round's answers do not. Once approved, the plan is closed: writing doesn't change what it decided without asking. If its foundation changes (a source doesn't exist, the target tool changed), the skill says so and reopens the plan.

## Checking the result

8. **Test by result, outside the conversation.** The output is read by a model, whose failures its author can't see, so it is tested by running it where the conversation can't help: the prompt on a realistic input, a knowledge file answering real questions with only the file, project instructions in a fresh chat. When the session can start a separate agent, the skill runs the test; when it can't, or the target tool is out of reach, it gives the user a ready test for a new conversation, because a model inside this conversation already knows the answer. On the light path, the test is offered in one line instead of run.

## Building a skill

9. **Each skill stands alone.** A skill can be installed on its own and reads nothing outside its folder, so it carries every shared rule it needs in full. A shared rule is changed in every skill that states it, in the same branch.
10. **A lean core.** `SKILL.md` loads in full on every activation, so it holds only the flow and the rules every phase needs, in under about 5,000 tokens; what a single step uses lives in `references/`. The description, under about 600 characters, says when to use the skill and when not to.
11. **Capabilities, not tool names.** A skill describes what the session can do ("if the session can start an agent") instead of naming tools or products, which change across Claude surfaces. What it knows about target platforms lives in `references/` and is checked against current documentation before use, because it goes stale.
12. **English inside, the user's language outside.** Skills, references and every file in the repo are written in English; the skills talk to the user in the user's language.

## Judging a proposal

1. Which real case does it come from?
2. Does it change behavior, or only wording?
3. Does it conflict with a principle? If so, is the case strong enough to change the principle?
4. Does it fit an existing skill, or does it need a new one?
5. Does it add size or turns without a visible gain?

A proposal for a new skill also answers:

6. Is its plan or test different from every existing skill's? Another kind of output with the same plan and test is a case in an existing skill.
7. Which requests does it take from a sibling, and is the sibling's scope changed in the same branch?
