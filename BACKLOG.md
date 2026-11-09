# Backlog

Ideas, bugs and debt for this plugin, managed with sensei's log skill. Each entry starts from a real case. Done work leaves this file: what changed goes to CHANGELOG.md.

## ai-prompt

### `[TO CONFIRM]` can end up inside a delivered prompt
- **Type:** Bug
- **Motivation:** consistency audit, 2026-11-08 (no case from real use). "Nothing invented" turns user facts into `[placeholder]` but also says "anything without a source is `[TO CONFIRM]`"; research.md marks tool details `[TO CONFIRM]` without saying where. A marker left in a pasted prompt is read by the target model as content.
- **Description:** state once in SKILL.md which marker goes where: `[placeholder: …]` inside the prompt for facts about the user's situation, `[TO CONFIRM]` only in the plan and the delivery notes.

### Agent task's first-run advice doesn't reach the delivery
- **Type:** Bug
- **Motivation:** consistency audit, 2026-11-08 (no case from real use). cases/agent-task.md says the delivery suggests a first run that asks before each change, or a dry run. delivery.md takes only the case file's pitfalls, so the safety advice is dropped.
- **Description:** delivery.md includes the case file's first-run advice when it has one.

## ai-knowledge

### Plan's sample entry is drafted before the writing rules are read
- **Type:** Bug
- **Motivation:** consistency audit, 2026-11-08 (no case from real use). references/writing.md is first read at 2.1, after the gate, so the sample entry approved at 1.3 (or in the light proposal) is drafted without its rules and rewritten at 2.1. The user approves text that doesn't survive.
- **Description:** read references/writing.md before drafting the sample entry, on both paths.

### Code-repository files aren't excluded
- **Type:** Bug
- **Motivation:** consistency audit, 2026-11-08 (no case from real use). ai-project leaves out files in a code repository; ai-knowledge doesn't. "Write an AGENTS.md" or "a coding style guide for Claude Code in our repo" match the description, and the skill's project rules (consultation sentence, project instructions) don't fit them.
- **Description:** leave out repository files (CLAUDE.md, AGENTS.md, agent configurations, skills) in Starting, matching ai-project's boundary, and add "otherwise handle it without the plugin" when the sibling can't be loaded.
- **Open questions:**
  - Also in the description, given the 600-character limit?

### Project size doesn't settle ChatGPT files
- **Type:** Bug
- **Motivation:** consistency audit, 2026-11-08 (no case from real use). The large-project rules apply only "when the plan says large", but ChatGPT files are to be written as if searched; a small ChatGPT project gets marked small and the excerpt rules are skipped. ai-project hands over "Size: read whole | searched", which ai-knowledge has to map onto small | large.
- **Description:** use one term pair in both skills (e.g. "read whole | searched") and say that any ChatGPT destination counts as searched.

## ai-project

### Custom GPTs, Gems and account-wide instructions have no owner
- **Type:** Bug
- **Motivation:** consistency audit, 2026-11-08 (no case from real use). ai-prompt leaves custom GPTs, Gems and account-wide custom instructions out; ai-project names only "a Gemini notebook". "Make a custom GPT for our sales team" would trigger ai-project, which has no platform file for GPTs and would apply project facts or fill them from memory.
- **Description:** settle who takes these requests and state it in Out of scope.
- **Open questions:**
  - Handle them without the plugin, or cover custom GPTs with a platform file?

## Plugin

### File search fact exists only in ai-knowledge's platform summary
- **Type:** Debt
- **Motivation:** consistency audit, 2026-11-08. ai-knowledge's references/platforms.md cites OpenAI's API "File search" (semantic and keyword search over chunks); ai-project's references/platforms/chatgpt.md, which principle 9 says holds the facts in full, doesn't.
- **Description:** add the fact with its source and check date to chatgpt.md, or drop it from ai-knowledge.

## Discarded

### Renaming a file after the gate is both forbidden and allowed
- **Description:** pick one rule between the gate ("writing doesn't rename a file without asking") and Fixes ("a file renamed" goes straight).
- **Why discarded:** either behavior is harmless: renaming after the test or asking first leads to the same result, so the fix isn't worth the change. (2026-11-08)
