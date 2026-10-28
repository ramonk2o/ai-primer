# Type: glossary

Terms the assistant must understand and use the way the project does: internal jargon, product names, acronyms, metrics, words that mean something specific here. It is consulted when a term appears in a request or must appear in an output.

## What makes it usable
- Each term with its meaning in this domain, not the dictionary's.
- The other words people use for it, so the model recognizes them in requests.
- Distinctions from look-alike terms, when confusing them causes errors.
- How to write the term in outputs, when there is a rule.

## Diagnosis questions
- Which terms do newcomers or clients misunderstand most, and which mean something different from their everyday sense?
- Which pairs get confused (two metrics, two plans, two statuses)?
- Which acronyms are used, and are any ambiguous?
- Which terms are never translated or always written a certain way? Who settles a disputed definition?
- Materials that help: an existing glossary or onboarding document, internal documents full of jargon, metric definitions from the reporting tool.

## Typical skeleton
1. What the glossary covers
2. Entries, alphabetical, in one format:

```
### Term
Definition in this domain, in one or two sentences.
- Also called: …
- Not to be confused with: … (the difference in one line)
- In outputs: … (only when there is a rule)
```

## Rules for this type
- Order alphabetically; group by topic only when entries are many and cluster.
- Define with what the term is and how it is measured or decided, not with a synonym ("Active member: a member with at least one transaction in the last 90 days").
- Every entry stands alone, and no two entries define the same thing.
- List the synonyms people actually use.
- Leave out terms any reader knows in their everyday sense, unless the user listed them; then cut them only with the user's agreement.
- Drop an empty field instead of filling it.

## Sample entry for the plan
One full entry, preferably for a term often confused with another.
