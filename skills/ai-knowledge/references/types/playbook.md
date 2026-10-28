# Type: playbook

A procedure the assistant follows for a recurring task: handling a complaint, reviewing a contract, qualifying a lead. It is consulted when the task starts and step by step during it.

## What makes it usable
- When it applies, and which neighboring task has another procedure.
- The inputs it needs, and what to do when one is missing.
- Steps in order, each an action with its result, and decisions written as conditions whose every branch goes somewhere.
- When to stop, ask or hand over to a person, and what "done" looks like.

## Diagnosis questions
- What sets the task off? Walk through the last real case, start to finish.
- Where does the person doing it decide, and on what basis?
- What goes wrong most often, and what is done then?
- When must the assistant stop and ask a person instead of deciding?
- Materials that help: an existing procedure, a real case, the output the task produces, the escalation rules.

## Typical skeleton
1. Purpose and scope
2. Inputs, and what to do if one is missing
3. Steps, numbered, with each decision inside the step where it happens
4. Exceptions and escalation
5. Output and done criteria

## Rules for this type
- One action per step, in the imperative ("Check the order status in the invoice; if it says 'shipped', go to step 5"), not a description of what the team usually does.
- Every branch ends somewhere: a later step, an output or an escalation. Cover what actually goes wrong, not only the happy path.
- Say which steps must be done exactly (a legal disclaimer, a fixed sequence) and what good judgment looks for in the others.
- Put escalation conditions in the step where they arise, and list them again in the exceptions section by name only.
- If a step depends on a fact that changes (a deadline, a fee), name where that fact lives or state its validity.

## Sample entry for the plan
One step with a decision, as it will appear, with its condition, both branches and an escalation if there is one.
