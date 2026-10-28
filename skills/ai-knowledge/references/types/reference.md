# Type: reference

Facts the assistant looks up: a product catalog, prices and fees, specifications, the rules of a program, eligibility criteria, an FAQ. It is consulted when a request needs a fact the model can't know.

## What makes it usable
- Scope: what it covers and what it doesn't.
- Each fact with its unit, currency, period and, when it changes, its validity.
- Comparable items with the same attributes in the same order, and limits and exceptions next to the fact they qualify.
- The source of decisive facts, and what to do when a fact isn't in the file.

## Diagnosis questions
- Which questions will it answer? List the most frequent ones.
- Where does each kind of fact come from, and which source wins if two disagree?
- Which facts change, how often, and who updates the file?
- Are there exceptions by region, plan, channel or customer type?
- Materials that help: the official source of each fact (price table, product sheet, terms) with its date, and the questions people actually ask.

## Typical skeleton
1. Scope and validity: what it covers, as of when, where facts come from
2. One section per entity or topic (one product, one plan, one rule)
3. Comparisons in a table when items share attributes
4. What isn't covered, and where to look instead

## Rules for this type
- One entity per section, so a question about it finds everything about it.
- Write facts as facts ("The Gold plan costs R$ 29.90 per month, billed monthly"), not prose about them.
- A rule with conditions goes in text under its entity, not in a table cell where its condition gets cut short.
- For an FAQ, write each question as people ask it, with an answer that stands alone without the question.
- Take from a source document only what the use cases need, and leave out facts the model already knows.
- Never keep two versions of a price or rule without saying which applies.

## Sample entry for the plan
One entity's section as it will appear, with its facts, units, validity and one exception.
