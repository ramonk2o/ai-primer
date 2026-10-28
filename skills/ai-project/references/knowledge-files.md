# Knowledge files

Used in the Files step, for each file in the approved Project plan.

## With ai-knowledge

If the session can load ai-knowledge, hand the file to it: the destinations, the project's purpose and use cases, the file's name, role, when it is used and type, its boundaries with the other files and live sources, the confirmed answers, the materials read with the origin of each piece of information, the gaps still open, and where to save it. It starts without its offer, treats what the plan approved as settled, and runs its own plan only for what the user hasn't approved. This skill keeps the Project plan and the delivery: between files, give one line of progress ("2 of 3 done: brand-voice.md; now the checklist"), and keep what ai-knowledge hands back for the instructions: the sentence on when to use the file, and any rule it says must apply in every chat. A rule that the approved plan's text doesn't already hold goes to the user as a proposal before it enters the instructions.

## Without it

These are the essentials that make a file usable by a model that never saw this conversation and often reads only an excerpt.

**Before writing.** Write from the plan: the file's role, when it is used, its type and the use cases it serves; each section serves one of them. If the plan didn't settle the file's content (what goes in, what is cut, a rule proposed to fill a gap), show an outline and one sample entry as it will appear, and ask for approval first.

**Structure.**
- A title that names the subject, then a short paragraph on what the file covers, what it doesn't and when it is used.
- Headings named by topic ("Refund conditions", not "Part 2"), in the order the file is used. Bullets for independent items, numbered lists for order, short tables only for comparable items. A file longer than about 100 lines starts with a list of its sections.
- Plain single-column text; layout is lost when files are parsed.

**Sections that stand alone.** Each section names its subject instead of "it" or "the above"; a rule's condition, exception and limit stay in its section; one term per concept, the one the project uses.

**Rules and facts.**
- Conditional rules as "If [condition], [action]", with a short reason when it isn't obvious.
- Observable criteria instead of adjectives: not "friendly tone" but "second person, short sentences, no jargon".
- Calm language, without all caps or "NEVER". When two rules can collide, say which wins.
- Numbers with units, currency and period; validity dates next to the facts; the current version in the main text.
- Items still unconfirmed keep `[TO CONFIRM]`, and the opening paragraph says so.
- Examples, when they show what a rule can't, as three to five varied, labeled input and output pairs; literal text in fenced code blocks.

**What stays out.** Notes on how the file was made; a "You are…" opening or any claim of authority over the instructions, since a file is consulted, not obeyed; common knowledge no use case needs; content that belongs to one job.

**Name and length.** A descriptive name in lowercase with hyphens (`refund-policy.md`). The length the use cases need, keeping every exact name, number, condition, exception and negation.
