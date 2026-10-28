# Case: reusable prompt

A template run many times, often by other people, with different inputs each time: classifying comments every week, drafting email variations from a brief, extracting fields from documents. What matters is not one good result but the same quality on every input, including the odd ones.

Standing instructions for an assistant project, read in every chat, are not this case; ai-project covers them. A template is pasted, with its inputs, at each use. When the user pastes the same template every day in the same place, say in one line that a project could hold it.

## What a good result needs
- The same format every time, so the output can be pasted, compared or loaded into a sheet.
- The same judgment on similar inputs, and a sensible answer on odd ones: empty, irrelevant, very long, ambiguous.
- A template someone else can fill in without asking how.

## Materials that help
Three to ten real inputs, including the hardest ones; outputs the user considers right for some of them; where the output goes; who will run it and how often.

## Diagnosis questions
- What do people do today without the template, and what goes wrong?
- What varies at each run, and what never changes?
- Does each run take one item or a batch? It changes the format, the odd inputs and the test inputs.
- What exactly comes out, in what format, and where does it go next?
- What are the categories, fields or rules, and who decided them? Which wins when two apply?
- What should happen when the input is empty, irrelevant or in another language?

## Writing the prompt
- **Fixed part and variables.** The instructions stay constant; what changes goes in slots with descriptive names, such as `{comment}` or `<document>`, used the same way everywhere.
- **Where the input goes:** short inputs in slots after the instructions; a long input before the request, which comes at the end.
- **Output format** stated exactly; when the output is loaded elsewhere, a structure that tool reads.
- **Rules for judgment:** the categories or criteria with a short definition each, and which wins when two apply.
- **Odd inputs:** what to return for each, so one bad row doesn't break the output.
- **Examples** only when the rules can't carry the judgment: three to five real cases, varied, including a hard one.
- **How to fill it in:** a line before the template, outside it, telling the person running it what goes in each slot.

## Typical shape
A line for the person running it; then the template: the task and its purpose, the rules, the odd-input rules, the output format, the examples if any, and the input slots last, unless an input is long.

## Pitfalls
- Examples that are all alike, so the model copies their accidents.
- Categories that overlap with no rule for which wins.
- A format described loosely ("a summary") where the next step needs fields.
- Tested only on easy inputs.
