# Handoff

Used to deliver the prompt: in the full path with the test's results, in the light path as the final reply. The prompt is finished; what is left is getting it to the right place in a form the user can paste, fill in and adjust.

## What the delivery holds
- **Where to run it:** app, model and mode, any setting to change, files to attach, and whether it goes in a new chat or a project.
- **The prompt** in a copyable block, exactly as it will be pasted, with nothing else inside. A chain comes as one block per step, numbered, each with what to paste into it and from where, as `chain.md` says.
- **What to fill in:** each placeholder or variable and what goes in it; for a template, the line telling the person running it what goes in each slot.
- **Translation:** when the prompt isn't in the user's language, a labeled translation below it, so they can check what it asks.
- **How to adjust:** three to five lines of "if the result comes out like this, change that", from the case file's pitfalls and the target's guidance.
- **The guidance it follows:** one line naming what you read and its date, and what to check if the app has changed since.
- **The real run is the final test:** one line inviting the user to bring the result back for an adjustment round.

## Where it goes
1. **A single prompt** is delivered in the reply.
2. **A template or a chain** will be reused or run in steps, so offer where to keep it from what this session can actually do: a file to download, an editable document, or a connected app where the user keeps prompts. Offer only what is available, recommend one, and keep the reply as the fallback.
3. **If the session can run the target itself,** offer it in one line and run it only with the user's agreement.

## Delivering
- Moving the prompt to a file or an app doesn't reword it; the Prompt plan still holds.
- Don't save or send a prompt that still holds placeholders without saying so in the same line.
- After moving it, check that line breaks, quotes, brackets and variable names survived; a lost brace breaks a template.
