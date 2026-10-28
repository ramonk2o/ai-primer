# Claude projects

Used when Claude is a destination: in the architecture, the instructions and the delivery. Last checked 2026-10-28 in the Claude Help Center: [Create and manage projects](https://support.claude.com/en/articles/9519177) and [RAG for Projects](https://support.claude.com/en/articles/11473015-retrieval-augmented-generation-rag-for-projects). Plans, numbers and screens change; check these pages before quoting them, and update this date when you revise the file.

## Creation screen
- The user creates the project with a name and a description. On Team and Enterprise plans, the screen can also set whether the project is private or visible to the organization, when admins allow it.
- Claude can't see the project's name or description. Nothing the project needs can live only there; suggest both anyway, because they help the user find the project.
- At the last check, free accounts could create up to five projects.

## Instructions
- Set under "Set project instructions" and applied to every chat in the project.
- No character limit is published. Keep them to what changes how the project acts.

## Project knowledge
- Documents, text files and code can be added, and everything added is used across the project's chats. No size or count limit is published.
- While it fits, project knowledge is loaded whole into every chat, so repetition across files is noise and a risk of conflict.
- As it nears the context limit, paid plans (Pro, Max, Team and Enterprise at the last check) switch to retrieval on their own, with a visual indicator: Claude searches the files and reads excerpts. The user can't turn this on or off, and it switches back if the knowledge shrinks.
- Anthropic recommends descriptive file names and citing documents by name in requests, because both improve that search. Include one test request that names a file when the knowledge is large.

## Live sources
- The help pages checked don't describe connected tools inside projects. When the design depends on one (a repository, Drive, Notion), ask the user to confirm the tool works in the project's chats, list it as a setup requirement, and test a fetch on the platform.

## Memory
- At the last check, memory was on by default for Free, Pro and Max; on Team and Enterprise an owner had to enable it.
- Each project keeps its own memory. Inside a project, Claude uses the project's memory plus the account's memory from chats outside projects, but not other projects'. Turning off "Use account memory" on the project page isolates it.
- Memory can be turned off for a single chat before its first message.
- Context isn't shared across chats except through project knowledge and memory. Treat memory as a complement: rules go in the instructions and the files. For a project with sensitive or client work, recommend deciding the account-memory setting at setup.

## Sharing
- Team and Enterprise plans, when admins allow it, with "Can view" (see the contents and chat) and "Can edit" (change instructions, knowledge and members). The creator removes access.
- Archiving keeps the project's sharing, members and knowledge.

## Consequences for the design
- Small projects are read whole: say which file governs which task and avoid overlap.
- Large projects are searched: name files descriptively and keep each section self-contained.
