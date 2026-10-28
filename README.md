# Metawork

Skills that help you work with LLMs. Each skill plans the piece with you before writing it — what it is for, what goes in, what a good result looks like — so the project, knowledge file or prompt you end up with does its job the first time.

The skills are written in English and talk to you in your own language.

## Skills

- **ai-knowledge** — plans and writes a knowledge file for an AI assistant project (a playbook, reference, profile, guidelines, glossary, example set, checklist or output template), then tests it with a reader who has only the file.

## Status

Early and experimental (before 1.0). Skills are being built one at a time. See [CHANGELOG.md](CHANGELOG.md) for what has changed.

## Install

### Claude Code

```
/plugin marketplace add ramonk2o/metawork
/plugin install metawork@metawork
```

The plugin updates when a new version is released.

### Claude apps (claude.ai, desktop, mobile)

Each skill can be installed on its own: zip its folder from `skills/`, with the folder at the root of the zip, and upload it as a skill in your Claude settings.

## How it is built

The principles every skill follows, and the questions used to judge a proposed change, are in [docs/principles.md](docs/principles.md).

## Contributing

Issues and pull requests are welcome. The most useful report is a real case: what you asked the skill, what it did and what it should have done.

## License

[MIT](LICENSE)
