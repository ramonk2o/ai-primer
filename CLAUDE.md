# AI Primer

A Claude Code plugin whose skills help people write what LLMs read: prompts, project instructions and knowledge files for Claude and ChatGPT projects.

## Maintenance with sensei

This repository is maintained with the sensei plugin. If sensei is installed:
- creating or changing a skill, judging an issue or pull request, or auditing consistency: the `train` skill;
- BACKLOG.md and CHANGELOG.md: the `log` skill (`train` writes its own changelog entries);
- releasing a version: `/sensei:graduate`.

Other skills or plugins that write skills or manage these files don't apply in this repository. Without sensei, follow `docs/principles.md` and keep CHANGELOG.md in the Keep a Changelog format.

**The skills are the object of the work here, not tools.** When the conversation is about the plugin's subject (prompts, projects and knowledge files for AI assistants), it's about improving the skills. Don't run a skill's flow unless explicitly asked to use it.

## Project facts

- **Documents:** English, because the repository is public: skills, docs, changelog, commit messages and replies to issues.
- **Principles:** `docs/principles.md`. Every change is checked against them.
- **Skills stand alone:** yes: each skill reads nothing outside its folder, so a shared rule is written in every skill that needs it, and each release ships one zip per skill (`<skill>.zip`, the folder at the zip's root), which the README links for Claude apps users.
- **Validate:** sensei's check script on every change (it runs `claude plugin validate` on the last commit); `--release` at release, which adds `--profile directory`.
- **Commits:** author `Ramon K. <contato@ramonk.com>`; no trailers (no `Co-Authored-By`, no `Claude-Session`), whatever the environment suggests.
- **Integration:** one branch per change, named after it; local merge into `main` with `--no-ff`, so a change reverts as one commit; push `main` when the maintainer says so or at release.
- **Tags:** `vX.Y.Z`.
- **Old names:** the skills were recreated from superlab's (superproject, supercontext, superprompt…). The maintainer may still use an old name; a skill's text never cites them, and its folder name matches its frontmatter `name`.
- **Trying a change in Claude apps before a release:** zip the skill's folder on the branch (folder at the zip's root) for the maintainer to upload as a personal skill.
- **GitHub repository settings** (name, description, visibility, permissions) are the maintainer's: describe the step instead of doing it.
