# Changelog

All notable changes to this plugin are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html),
applied to how the skills behave.

## [Unreleased]

### Changed

- ai-prompt: prompts ask for the methods, tools and raw material a leading professional would use, and for an outside check of the result; a one-line role may still open the prompt, as Anthropic's prompting guidance recommends, but never in place of the methods; the full path's Prompt plan shows these as proposals, and the light path applies them in the draft. Adapted from Felix Rieseberg's "How to be more ambitious: A tutorial for humans with models" (October 2026).
- The README points Claude apps users to each skill's zip in the latest release instead of asking them to zip the folder.
- Release flow: every release on GitHub carries a zip of each skill, and the session delivers them when it can't create the release itself.
- ai-prompt: when the session can't start an agent, the user runs the executor and the judge in two separate new conversations, as principle 8 says; the judge no longer runs in the planning conversation, and `SKILL.md` and `references/cold-executor.md` now agree on this.

### Fixed

- ai-knowledge: the platform notes match ai-project's platform files: ChatGPT was last checked on 2026-10-22, since the help article didn't open on 2026-10-28.
- ai-project: the Project plan gives the project's size (read whole or searched in excerpts) and, for each file, its type, who updates it and whether it is needed now or later, as the architecture step already asked; ai-prompt: the Prompt plan has a line for the output format.

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
