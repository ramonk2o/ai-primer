# Case: deep research

A prompt for a research mode that browses and reads for minutes, sometimes longer, and returns a report. It can't be steered once it starts, so the question, the scope and the shape of the report are settled before it runs. This skill writes the prompt; it doesn't do the research. If the user wants the research done now, in this conversation, that is doing the task: say so in one line and leave the skill.

## Check first whether a prompt is worth it
Look up, as `research.md` says, whether the mode asks clarifying questions or shows an editable plan before it runs. If it does and the question is simple, recommend going straight to the mode with a one-line question, without this skill. If it does and the stakes are high, the prompt can be shorter: it brings what the mode can't ask about (the use of the report, what the user already knows, the sources that count).

## What a good result needs
- An answer to the question the user actually has, at the depth they need, not a survey of the topic.
- Sources of the kind the question calls for, cited where each claim is made.
- A report shaped for its use: a decision, a briefing, a comparison.
- What the research couldn't find, said plainly instead of filled in.

## Materials that help
What the user already knows or has (a file, an earlier report, internal figures); who will read the report and what they will do with it; sources they trust or distrust; a report they found useful.

## Diagnosis questions
- What decision or understanding will the report serve? What would make it useless?
- What does the user already know, so the research doesn't repeat it?
- Which dimensions must it cover, and which are out? What period and which places?
- Which kinds of source count (official statistics, regulators, papers, company filings) and which don't?
- How long should the report be, in what language, and for which reader?

## Writing the prompt
- **The goal, not the steps.** What the user needs to learn or decide and why; prescribe steps only when a source must be checked first.
- **Scope:** the question, the dimensions, the period and places, the depth, and what is out.
- **Sources:** the kinds to prefer and those to treat with care; primary sources over summaries where the question turns on data.
- **Evidence:** claims checked across sources, conflicting findings shown rather than averaged, and how confident the evidence makes each position on a contested question.
- **The report:** sections in order, tables where they compare, citations next to each claim, length, language and reader.
- **Gaps:** say what couldn't be found or confirmed, instead of estimating.
- **No invented preference:** a dimension the user didn't settle is marked open; a guessed preference sends the whole run in the wrong direction.

## Typical shape
The goal and its use; the context the user already has; the scope and what is out; the sources; the shape of the report; the gaps rule. A few short paragraphs, since the mode does the expanding.

## Pitfalls
- A topic ("BNPL in Brazil") where a question belongs ("whether BNPL use among lower-income users in Brazil grew after 2024, and why").
- Steps that script the research and stop the mode from following what it finds.
- No source criteria, so press releases weigh as much as statistics.
- No reader or use, so the report comes back as a generic overview.
