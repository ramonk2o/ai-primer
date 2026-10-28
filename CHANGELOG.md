# Changelog

All notable changes to this plugin are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html),
applied to how the skills behave.

## [Unreleased]

### Added

- ai-project: designs a Claude project, ChatGPT project or Gemini notebook with the user before setting it up. The Project plan carries the instructions' key text as it will appear; live sources reached through a connected tool (a repository, Drive, Notion) are a layer of their own, and a project with no files is a normal result; Claude is the reference design. The project is tested with a cold reader who has only the instructions and the files, and fixes that add a rule, a fact, a file or a source go back to the user as proposals before delivery.
- ai-knowledge: plans a knowledge file with the user before writing it (use cases, a triage of what goes in, and a File plan with a sample entry), writes it for how assistants read project files, small or retrieved in pieces, and tests it with a cold reader who has only the file and any overlapping neighbor files.
- Repository skeleton: README, MIT license, changelog, plugin and marketplace manifests, skill principles and the maintenance project's instructions.

### Changed

- Principle 8: a fix the test calls for that adds a rule or a fact is a proposal the user approves; only fixes that change no decision go straight.
- The plugin is shown as Metawork, with a capital M; its install name stays `metawork`.
