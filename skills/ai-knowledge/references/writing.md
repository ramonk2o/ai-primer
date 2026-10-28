# Writing the file

Used in step 2.1. These rules make a file usable by a model that never saw the conversation. They hold for every type; each type file adds its own skeleton and rules.

## Contents
- Who reads the file
- Every line costs attention
- Structure
- Sections that stand alone
- Large projects
- Rules
- Examples and literal text
- Facts that change
- Format and length
- What stays out

## Who reads the file

- Write for a capable colleague who knows the world but not this project. Explain what is specific to the project (its rules, names, criteria, exceptions) and skip what any capable reader already knows.
- A file is consulted, not obeyed. It doesn't open with "You are…" or claim authority over the project's instructions; a file that poses as a system prompt competes with the instructions instead of supporting them.
- In a small project the model reads the whole file at once; in a large one it searches the project's files and reads the pieces it finds. Write every file so a piece still makes sense, and apply "Large projects" when the plan says large.

## Every line costs attention

A model's accuracy drops as its context fills, and text that looks relevant but isn't hurts it most.

- Each paragraph earns its place by changing what the model does in a use case. If removing it changes no answer, remove it.
- Don't repeat a fact or rule in two places with different words, in this file or across the project's files. The model can't tell whether two near-identical versions mean the same thing, and picks one differently from chat to chat. Name where the other copy lives instead.
- A superseded version of a rule or fact leaves the file, or moves to a section labeled as old (see "Facts that change").
- Start lean. Add a rule or an example to fix a failure the cold reader or real use showed, not to anticipate every case.

## Structure

- Open with a title that names the subject and a short paragraph saying what the file covers, what it doesn't, and when to consult it.
- Use Markdown headings named by topic ("Refund conditions", not "Part 2"). Headings are what both a reader and a search find first.
- Order sections by use: what is consulted most, or first in the task, comes first. Files looked up by name, such as a glossary, follow their type's order.
- Bullet lists for independent items, numbered lists when order matters, tables only for items that share the same attributes (a catalog, a price list). Two heading levels and one level of nesting cover almost everything.
- Plain, single-column text. Columns, text boxes and text inside images are lost when files are parsed.
- A file longer than about 100 lines starts with a short list of its sections, so a partial read still shows the whole scope.

## Sections that stand alone

- Each section's heading names its subject: the product, program, period, region or audience.
- Keep a rule's condition, exception and limit in the same section, ideally the same bullet, as the rule.
- Use one term per concept, the same term the project uses. Mixing synonyms ("client", "customer", "account") makes the reader wonder whether they differ, and makes searches miss.
- Don't make a section depend on another ("as explained above"). If it needs a definition, use the exact term so the glossary entry is found.

## Large projects

When the project's knowledge nears the context limit, the model reads short retrieved pieces, which may come without the heading above them.

- Name the subject inside the section's text too, not only in its heading, and repeat it instead of "it", "the company" or "this quarter".
- Keep each rule, with its condition and exception, short enough to fit in one piece; split a long section into subsections by subject.
- Split a long table by entity, each under its own heading, or name the entity in every row, since a retrieved piece of a table loses its header row.

## Rules

- Write conditional rules as "If [condition], [action]". Say what to do, not only what to avoid: "Write prices with the currency symbol and two decimals" beats "Don't write prices loosely".
- Give the reason for a rule that isn't obvious, in one short sentence. A model generalizes from the reason to cases the rule didn't foresee.
- Replace adjectives with observable criteria: not "friendly tone" but "second person, short sentences, no jargon, one emoji at most".
- Write in calm, plain language. All caps, "CRITICAL" and "NEVER" make current models apply a rule rigidly and out of context.
- No two rules may contradict each other. When rules can collide, say which wins ("If a client contract says otherwise, the contract wins").
- Match strictness to risk: exact wording where a mistake is costly (legal text, prices, a fixed format), a principle with room for judgment where several answers are fine.

## Examples and literal text

- Use examples when they show what a rule can't say alone (tone, level of detail, a format), or when they are the file's subject.
- Show input and output pairs, varied in length, topic and structure so the model doesn't copy a surface pattern. Three to five usually teach more than one or ten.
- Say what each example illustrates, and make sure every behavior an example shows is also stated as a rule.
- Label synthetic examples as such; never present them as real cases or real data.
- Keep literal text (an approved message, a template, a schema) in a fenced code block. When literal text and guidance mix closely, XML-style tags (`<example>`, `<approved_message>`) can delimit them; don't wrap the whole file in tags or duplicate Markdown and XML.
- In templates, mark variables as `{{field_name}}`, say which are required and what to do when the data is missing. Placeholders belong in templates, never as stand-ins for facts.

## Facts that change

- Give numbers with units, currency and the period they refer to.
- State a fact's validity next to it ("valid from 2026-07-01") and write the current version in the main text. A superseded version goes, or moves to a section labeled as old; never leave two versions side by side without saying which applies.
- Keep the source of decisive facts and rules (document and section, link, or "stated by [role]") where it helps someone apply or update them, after the item or in a sources line at the end of the section.
- Items the user agreed to deliver unconfirmed keep their `[TO CONFIRM]` marker next to them, and the opening paragraph says marked items are not confirmed.

## Format and length

- Markdown in UTF-8, with a descriptive file name in lowercase with hyphens (`refund-policy.md`, `brand-voice.md`). Assistants search files by name, and `doc1.md` matches nothing.
- Markdown is the default because models and people both read it well, every platform accepts it, and its headings mark sections for search. Data such as a price list also stays in Markdown, split by entity. If the user wants another format, say this in one line and follow their choice; JSON is a poor container for prose, and PDF and slides lose structure when parsed.
- Respect a stated length. Without one, use the length the use cases need, and don't state a token count, since it varies between models.
- Don't save space with obscure abbreviations or fragments that drop a condition or a negation. Short is good; ambiguous isn't.

## What stays out

- The interview, its transcript, and notes about how the file was made.
- Generic introductions, motivation and filler.
- Common knowledge no use case depends on.
- Content that belongs to a single task (one campaign's brief, one client's exception), unless the file is about it.
- Prompt-engineering advice, unless that is the file's subject.
