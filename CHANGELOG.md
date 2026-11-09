# Changelog

All notable changes to this plugin are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html),
applied to how the skills behave.

## [Unreleased]

### Changed

- ai-prompt: on the full path, the Prompt plan shows the prompt's hardest rule as it will read, so the user judges text before approving.
- ai-prompt: a one-off ask whose result goes to a client or to other people, or that a consequential decision rests on, gets the offer instead of the light proposal; called by name, a light case starts the light proposal; "improve this prompt" asks in one line whether a run went wrong before choosing between diagnosis and a new prompt.
- ai-knowledge: leaves out files that live in a code repository, in its description too; a file for a platform it has no facts on, such as a custom GPT, is written as portable Markdown with a note saying so.
- ai-project: leaves out custom GPTs, Gems and account-wide custom instructions.
- ai-knowledge: the plan's sample entry follows the writing rules, so the approved text is the text written; size is "read whole | searched", as ai-project hands it over, and any ChatGPT destination counts as searched.
- ai-prompt: `[TO CONFIRM]` stays in the plan and the delivery notes, never inside the prompt; the delivery carries the case file's first-run advice, such as a dry run for an agent task.

## [0.3.1] - 2026-11-04

This version leaves examples out of open work in prompts and knowledge files.

### Changed

- ai-prompt, ai-knowledge and ai-project: examples are left out of open work (ideas, analysis, plans, research questions), where they narrow what current models explore; they stay for formats, tones and borderline cases.

## [0.3.0] - 2026-11-04

This version changes how ai-prompt checks a prompt: the user's first real run, judged against a checklist, replaces the executor-and-judge test.

### Changed

- ai-prompt: it no longer tests the prompt with a separate executor and judge; the user's first real run on the target is the test, and the delivery carries the goal's statements as a checklist for it, with a result that misses one coming back as an adjustment round. Agent tasks get a suggested first run that asks before every action, or a dry run. `references/cold-executor.md` is removed, and principle 8 names ai-prompt as its exception.
- ai-prompt: its description also leaves out system prompts for an API, as its scope already did.
- ai-knowledge and ai-prompt: rules stated twice in the same `SKILL.md` are stated once.

### Fixed

- ai-knowledge and ai-project: reading a whole file is described as what a small Claude project does, not every platform; ChatGPT doesn't say whether it reads files whole.

## [0.2.0] - 2026-11-04

This version removes Gemini support, which breaks use for anyone who relied on it.

### Changed

- ai-prompt: prompts ask for the methods, tools and raw material a leading professional would use, and for an outside check of the result; a one-line role may still open the prompt, as Anthropic's prompting guidance recommends, but never in place of the methods; the full path's Prompt plan shows these as proposals, and the light path applies them in the draft. Adapted from Felix Rieseberg's "How to be more ambitious: A tutorial for humans with models" (October 2026).
- The README points Claude apps users to each skill's zip in the latest release instead of asking them to zip the folder.
- Release flow: every release on GitHub carries a zip of each skill, and the session delivers them when it can't create the release itself.
- ai-prompt: when the session can't start an agent, the user runs the executor and the judge in two separate new conversations, as principle 8 says; the judge no longer runs in the planning conversation, and `SKILL.md` and `references/cold-executor.md` now agree on this.
- ai-knowledge and ai-project: a light-path request whose material is in the message gets the light proposal in the first reply instead of a turn spent offering the skill, as ai-prompt already did; principle 2 says so.
- All three skills: when the user declines the skill or asks for just the result, it skips the rounds, gate and test but still writes by its rules, marking gaps instead of inventing them, instead of leaving the skill.
- ai-prompt: on the light path, the target is looked up only when the recommendation or the prompt depends on it; when the user already fixed where it runs, the draft comes without browsing.

- ai-prompt: `references/handoff.md` is now `references/delivery.md`, the name ai-project uses; ai-project's rule on the test calls its reader the cold reader and its skipped-test note "Cold reader: not run", as its delivery template does.

### Fixed

- ai-knowledge: the platform notes match ai-project's platform files: ChatGPT was last checked on 2026-10-22, since the help article didn't open on 2026-10-28.
- ai-project: the Project plan gives the project's size (read whole or searched in excerpts) and, for each file, its type, who updates it and whether it is needed now or later, as the architecture step already asked; ai-prompt: the Prompt plan has a line for the output format.
- ai-project and ai-knowledge describe the handover of a knowledge file with the same list on both sides (adding the project's size, the use cases the file serves, its type, who updates it and where to save it), and say that the handed file follows the project's path and is tested and delivered with the whole project, not on its own.
- Claude and ChatGPT platform notes say the same in ai-project and ai-knowledge: retrieval in Claude projects runs on paid plans, now including Ultra, and holds up to about 10 times more (checked 2026-11-03); ChatGPT's help doesn't say whether files are read whole or in excerpts, so both write for excerpts.
- On the light path of all three skills, answers that only fill gaps or adjust wording approve the plan, as ai-prompt already said, so the user isn't asked to approve twice; the rule on gates says so too.
- ai-prompt: the light path points to the "four questions" in `references/research.md` by the name that file uses.
- README: says that updates aren't automatic for this marketplace by default, and how to update or turn auto-update on, instead of promising updates on release.

### Removed

- Gemini support. ai-prompt no longer considers Gemini when recommending a model and mode, and writes for it only as for any other assistant the user names, from its official guidance. ai-project designs Claude and ChatGPT projects only: a project for another platform is out of scope, though one can still be ported from it. ai-knowledge drops its Gemini notebook notes and keeps writing portable Markdown.

## [0.1.0] - 2026-10-28

### Added

- ai-prompt: helps the user work out what they want before writing a prompt (what the result is for, what would make it good or bad, which decisions the prompt would leave to the model), recommends one model and mode in ChatGPT, Claude or Gemini from current official docs and the user's plan, and writes the prompt for it. Covers one-off asks, conversation openers, deep research, agent tasks, reusable templates, chains across chats and models with the handover between steps, model-only questions and diagnosis of a prompt that misfires. Prompts are tested with a cold executor and a separate judge.
- ai-project: designs a Claude project, ChatGPT project or Gemini notebook with the user before setting it up. The Project plan carries the instructions' key text as it will appear; live sources reached through a connected tool (a repository, Drive, Notion) are a layer of their own, and a project with no files is a normal result; Claude is the reference design. The project is tested with a cold reader who has only the instructions and the files, and fixes that add a rule, a fact, a file or a source go back to the user as proposals before delivery.
- ai-knowledge: plans a knowledge file with the user before writing it (use cases, a triage of what goes in, and a File plan with a sample entry), writes it for how assistants read project files, small or retrieved in pieces, and tests it with a cold reader who has only the file and any overlapping neighbor files.
- Repository skeleton: README, MIT license, changelog, plugin and marketplace manifests, skill principles and the maintenance project's instructions.

### Changed

- Principle 8: a fix the test calls for that adds a rule or a fact is a proposal the user approves; only fixes that change no decision go straight.
- ai-knowledge: a fix from the cold reader that adds a rule, a fact or an example is a proposal the user approves before delivery, as principle 8 now says.
- The plugin is named AI Primer; its install name is `ai-primer`.
- ai-knowledge: prompts for image, video or audio tools are handled without the plugin instead of being sent to ai-prompt.

### Fixed

- ai-knowledge: its platform notes give Gemini notebooks' source limit (up to 600, depending on the plan) instead of saying Google hadn't published one.
