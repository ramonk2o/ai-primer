# Architecture

Used in the Architecture step, to decide what goes in the instructions, the knowledge files, the live sources and the chat, and which files the project needs.

## Layers

| Layer | Content |
|---|---|
| Instructions | Purpose, limits, recurring behavior, requirements indispensable to every task, when to use each file and live source, and how to handle gaps and conflicts. |
| Knowledge files | Stable facts, conditional procedures, detailed criteria, style, examples, vocabulary and formats. |
| Live sources | Knowledge that changes faster than anyone would re-upload it and that a tool the project's chats can use reaches: a repository, a Drive folder, a Notion database. |
| The chat | Briefing, goal, deadline and decisions that apply to one deliverable. |

- A requirement indispensable to every task stays in the instructions even when a file details it, because instructions are always read and files may not be.
- Don't copy a file's content into the instructions. Separate durable knowledge from one-job exceptions.
- Original sources can stay attached when reading them directly adds value (visual references a summary doesn't capture).
- Nothing the project needs depends on memory, on members' personal instructions or on the project's name or description.

## File or live source

- Use a live source when the knowledge has an owner and a home elsewhere, changes between uses, and the destination's chats can reach it with a connected tool (check the platform file). An uploaded copy of it drifts from the original without anyone noticing.
- Use a file when the knowledge is settled, or when no tool reaches its home; then the plan names who updates the file and when.
- For each live source, the instructions say what it is, when to fetch it, that what is fetched wins over memory, attachments and earlier fetches, and what to do when the tool fails: say so and don't answer as if the source had been read. The delivery lists the connection as a requirement, and one test request depends on fetching it.

## File map

- Use the smallest set of sources that serves the use cases. Each file justifies itself through a request; don't create a playbook, glossary, checklist and template by default. When a few lines in the instructions would do, write the lines instead of a file. A project with instructions and no files is a normal result.
- Combine content used together; separate content with different triggers, update cycles or owners. Platforms cap files per project, small projects are read whole (repetition becomes noise and a risk of conflict), and large ones are searched in excerpts (descriptive names and self-contained sections decide what is found).
- For each file, settle a descriptive name, its role, when it is used, its type (playbook, reference, profile, guidelines, glossary, examples, checklist or output template), its sources or gaps, and whether it is needed now or later.

## Small and large projects

- **Read whole** (a small Claude project, or a few short files): the model sees every file in every chat, so the instructions say which file governs which kind of task and which wins when two apply. Avoid overlap more than you save space.
- **Searched in excerpts** (a large Claude project in retrieval mode, ChatGPT files, a notebook with many sources): the instructions say when to open each file, by name, and each section must stand on its own, since the model may see only that part.
- When unsure, write for excerpts: it also works when the files are read whole.
