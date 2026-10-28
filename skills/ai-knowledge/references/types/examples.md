# Type: examples

A set of examples that shows the assistant what good output looks like: approved posts, model replies to clients, reviewed briefs, classified cases. It is consulted when the output's tone, level of detail or format is hard to describe in rules.

## What makes it usable
- Each example as a pair: the input or situation, and the approved output.
- What each example shows, in one line: the decision or quality it illustrates.
- Variety: examples that teach different decisions, not variations of one.
- A label on whether each example is real or written for the file.

## Diagnosis questions
- Which outputs will the assistant produce, and which are hard to get right?
- Are there approved real outputs, and can they be used without personal or confidential data?
- What makes a good one good? Ask about each candidate.
- Which situations differ enough to need their own example (a complaint vs a compliment)?
- Materials that help: approved outputs with the request that produced them, rejected outputs with the reason, reviewers' comments.

## Typical skeleton
1. What the examples are for, and the rules they illustrate, in short
2. Examples grouped by situation:

```
### [Situation in a few words]
Shows: [the decision or quality this example illustrates]
Input: …
Output:
[the approved output, verbatim]
```

3. Poor and good pairs, when a common mistake is worth showing

## Rules for this type
- Choose examples by the decisions they teach: each hard situation in the use cases gets its own small set, usually three to five.
- Vary length, topic and structure within a situation, so the model learns the principle and not a shape to copy.
- Keep the input with every output, and make sure no example contradicts the guidelines.
- Replace personal and confidential data with clearly fictional stand-ins, and say so.
- Keep a long approved output whole only if its length is part of what it teaches.

## Sample entry for the plan
One complete example with its "Shows" line, input and output.
