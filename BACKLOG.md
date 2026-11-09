# Backlog

Ideas, bugs and debt for this plugin, managed with sensei's log skill. Each entry starts from a real case. Done work leaves this file: what changed goes to CHANGELOG.md.

## Discarded

### Renaming a file after the gate is both forbidden and allowed
- **Description:** pick one rule between the gate ("writing doesn't rename a file without asking") and Fixes ("a file renamed" goes straight).
- **Why discarded:** either behavior is harmless: renaming after the test or asking first leads to the same result, so the fix isn't worth the change. (2026-11-08)
