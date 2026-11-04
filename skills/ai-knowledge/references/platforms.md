# Platforms

Used in step 0.2 when the destination is known or the project is large. These notes say how each platform reads project files, as checked on the date beside each one. Platforms change often, so before relying on a note in a reply, check the platform's current official documentation; if it differs, follow the documentation and tell the user the note is outdated. When the platforms would lead to different choices, write for Claude.

## In common
- Project instructions are read in every chat; files are material the model consults. A rule that must always apply needs a line in the instructions.
- None of them promises which files or passages a given answer will use.

## Claude projects (checked 2026-11-03)
- Project knowledge is loaded into the context while it fits. As it nears the context limit, a project on a paid plan (Pro, Max, Ultra, Team or Enterprise) switches on its own to retrieval: the model uses a project knowledge search tool and reads the passages it finds, with capacity up to about 10 times larger. The user can't choose the mode; a visual indicator shows it.
- Anthropic's advice for retrieval: descriptive file names, related documents in the same project, and naming a specific document in the question.
- Source: Claude Help Center, "Retrieval augmented generation (RAG) for Projects".

## ChatGPT projects (checked 2026-10-22; the help article couldn't be opened on 2026-10-28)
- Files per project depend on the plan: 5 on Free, 25 on Go and Plus, 40 on Pro, Business, Edu and Enterprise; up to 10 per upload. Over the limit, OpenAI suggests combining files or splitting the work across projects.
- Project instructions set how ChatGPT responds and override the user's global custom instructions inside the project; files supply reference material. The help article doesn't say whether files are read whole or retrieved in excerpts, so write them for excerpts; OpenAI's file search in the API combines semantic and keyword search over chunks.
- Source: OpenAI Help Center, "Projects in ChatGPT"; OpenAI API docs, "File search".
