# Delivery

Used in the Deliver step. Take every setting and limit from the destination's platform file, as checked, and keep to what the user has to do or decide.

## Files

Save everything as `.md` files in a dedicated folder, in the requested location or the working folder, because the user will paste and attach them. Don't overwrite unrelated files. Without a way to write files, deliver the content in copyable blocks and say it wasn't saved.
- **Instructions:** one file per destination (for example `instructions-claude.md`), holding only the text to paste.
- **Knowledge files:** shared by every destination.
- **Setup and testing guide:** full path only, named in the project's language (for example `setup-and-tests.md`), labeled as a guide for the user that isn't attached to the project.

If a connected tool can write directly into the destination project, offer it and write only with the user's agreement.

## Name and description

Always suggest a project name and, where the creation screen has the field, a one- or two-sentence description of what the project is for and for whom, ready to paste. Say in one line that the model doesn't see them, so they only help the user find the project.

## Test requests

Write them from the use cases: a common one, one that combines sources, and one with missing data or an ambiguous ask, whose success is a specific question instead of an invented answer. For each, name the sources it should use and an observable success signal. Add one request that depends on each live source being fetched, and, for a large Claude project, one that names a file, to check retrieval. Say these run on the platform; the cold reader was only a check.

## Guide (full path)

```markdown
# {{Project name}} — setup and tests

A guide for setting up the project. It isn't attached to it.

## Name and description
- **Name:** {{name}}
- **Description:** {{one or two sentences}} (only where the screen has the field)

## Sources
| Source | Role | When it is used |
| --- | --- | --- |
| `{{file.md}}` or {{live source}} | {{role}} | {{trigger}} |

## Set up in {{destination}}
1. {{Decisions before or at creation: memory, sharing, connections the live sources need}}.
2. Create the project and paste `{{instructions file}}` into the instructions field.
3. Add {{knowledge files}}.

## Tests
| Request | Should use | Success signal |
| --- | --- | --- |
| {{request}} | {{sources}} | {{observable signal}} |

## Check and open items
- Cold reader: {{what diverged and what changed, or "not run"}}
- {{Only open items that affect the result}}
```

With more than one destination, keep one sources table and one test table, and write a short setup section per destination.

## In the chat

Finish with the files, the name and description (so they can be copied without opening anything), how to set up and test in a few lines, the test's result in one line, and only the open items that affect the result. On the light path, the setup steps and the test requests go here instead of a guide. Don't present the package as complete if an essential file is missing; if the user asked only for the architecture, deliver the plan and list what is still to produce.
