# Writing the project instructions

Used for the instructions' text in the Project plan and in the Instructions step. The instructions are the one layer the platform always reads, so they carry the purpose, the requirements indispensable to every task and when to use each source.

## What goes in

- Who the project serves, with what work, the most common requests and what a good deliverable looks like, in observable terms, including its usual format and length.
- What the project doesn't do, when a likely request falls outside it, and what to do instead.
- The requirements listed in the Project plan, each with a short reason.
- When to use each file and live source, inside the instructions themselves, so finding a file never depends on first opening an index.
- How to handle gaps and conflicts, proportionate to the project.
- When a decision affects future work, which file or source should change, and who changes it.

Write concrete, concise, self-sufficient guidance, with only what changes how the project acts. Leave out generic behavior the assistant already has.

## When to use each source

- State the situation or intent, the exact file and what to apply: "When creating or reviewing public brand copy, apply the rules and examples in `brand-voice.md`; before delivering, check it against `publishing-checklist.md`."
- Prefer intents and stages of the work over keywords, because users rarely use the words you anticipated.
- In a project read whole, phrase it as which file governs which task, and say which wins when two apply; in one searched in excerpts, phrase it as when to open which file (see `architecture.md`).
- Allow combining files in mixed tasks. Add an exclusion ("don't use X for Y") only when it prevents a likely confusion.
- Cite each file by its exact saved name; the name also guides search.
- For a live source, say what to fetch and when, that the fetched version wins, and what to say when the tool fails.
- Fold in the sentences ai-knowledge handed back for each file, adapted to the instructions' wording.

## Gaps and conflicts

Include what fits the project:
- A needed source can't be reached: say so, ask for the content when it is decisive, and if it is possible to move on, mark what is provisional.
- A piece of data that changes the deliverable is missing: ask a specific question instead of inventing features, numbers or internal rules, with examples of what must never be invented.
- General rules, exceptions approved for one job and ideas under discussion are different things; a brainstorm does not become policy.
- Sources conflict on something decisive: use each source's known authority and scope and ask when it still matters, without silently picking the most recent one. An explicit correction from the user replaces earlier data.

## What stays out

- Commands to invoke skills: they build the project; they aren't part of using it.
- Requests to show internal reasoning, and promises of tools or features the destination doesn't offer (check the platform file).
- Briefings and decisions that belong to one deliverable.
- All caps, "CRITICAL" or "NEVER": they make models apply a rule rigidly and everywhere. Give the reason instead.

## Shape

Use this order and drop what doesn't change how the project acts:
1. Purpose: who, what work, common requests, a good deliverable, what the project doesn't do.
2. Requirements for every task, each with its reason.
3. When to use each file and live source.
4. Gaps and conflicts.
5. Upkeep: what to say when a decision should change a file or source.

## Per destination

**Claude.** Direct prose in short paragraphs, with headings only when the text grows long enough to need them. Give the reason for each important rule: Claude generalizes from the reason, and emphatic warnings make it overcautious. Use XML tags only to set off material of a different nature, such as a literal example. An excerpt:

```markdown
You support the marketing team in writing and reviewing posts for the brand's social channels. Most requests are a first draft from a briefing or a review of a draft someone pasted; a good answer is ready to publish, in the channel's format, with any change explained in one line.

Never state a price, a date or a benefit that isn't in the briefing or in `offers.md`, because a wrong offer becomes a public commitment; ask instead.

When writing or reviewing copy, `brand-voice.md` governs tone, vocabulary and the words to avoid. Before delivering, check the piece against `publishing-checklist.md`.
```

**ChatGPT.** Markdown headings for purpose, behavior, when to use the files, and gaps; explicit "When X, do Y" conditions.

**Gemini.** Role, constraints and output format first; direct and concise, with ambiguous terms defined, and one structure throughout (Markdown headings or XML-style tags, not both). Say when web search is allowed and when only the notebook's sources count. If the project needs detailed or conversational answers, ask for them, because Gemini tends toward short ones.
