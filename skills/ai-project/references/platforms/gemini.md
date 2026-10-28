# Gemini notebooks

Used when Gemini is a destination: in the architecture, the instructions and the delivery. Last checked 2026-10-22 in Google's help centers: [Organize your projects with notebooks in Gemini Apps](https://support.google.com/gemini/answer/16972047) (checked again 2026-10-28), [Notebooks in Gemini Apps](https://support.google.com/gemininotebook/answer/17003757), [Gemini Notebook plans](https://support.google.com/gemininotebook/answer/16213268), [Add sources to your notebook](https://support.google.com/notebooklm/answer/16215270), [Gemini Notebook FAQ](https://support.google.com/notebooklm/answer/16269187), and Google's [prompt design strategies](https://ai.google.dev/gemini-api/docs/prompting-strategies). This area changes fast; check these pages before quoting them, and update the date when you revise the file.

## What the destination is
- A notebook groups chats, custom instructions and sources about one subject. It is created from the Gemini menu ("New notebook") and is the same notebook in the Gemini Notebook app (earlier called NotebookLM): sources, instructions and renames sync between the two.

## Creation screen
- The user names the notebook and can start with a prompt. At the last check there was no description field, so suggest a name only.
- Whether the model sees the notebook's name isn't documented; don't rely on it.

## Instructions
- Custom instructions are set in the notebook's settings and are one set for both apps. No character limit is published.
- Grounding differs by app: in Gemini, notebook chats can also use web search and other Gemini tools; in Gemini Notebook, chat answers use only the sources. Say in the instructions when the web is allowed and when only the sources count.

## Sources
- Files from the device (PDF, documents, spreadsheets, images, audio, text and Markdown), Google Drive files, websites and pasted text. A notebook can't use another notebook as a source.
- Up to 600 sources depending on the Google AI plan; at the 2026-10-22 check, 50 on the standard plan, 100 on Plus, 300 on Pro, and 500 or 600 on Ultra, each up to 500,000 words or 200 MB.
- With many sources, the notebook retrieves the most relevant parts for each question, so descriptive names and self-contained sections matter.

## Live sources
- Google Drive sources sync automatically, so knowledge kept as Google Docs works as a live source with no connector. Comments and footnotes in Google files aren't imported.

## Memory and activity
- Notebook memory, auto-saved chats, adding existing chats and Drive sources require the user's Keep Activity setting. Without it, the notebook still answers from its sources and instructions.

## Sharing
- Shared notebooks aren't listed in the Gemini sidebar and open in Gemini Notebook. At the 2026-10-22 check, a notebook containing Gemini chats couldn't be shared. If the project will be shared, recommend creating and sharing it in Gemini Notebook before the team starts chatting.

## Availability
- Rolled out gradually in 2026 on web and mobile, and in the Mac app. Not available to users under 18. Availability for Workspace and education accounts depends on the account and the admin, and users in the European Economic Area connect Gemini Notebook manually; ask the user to confirm they see notebooks before designing for them.

## Writing instructions for Gemini
- Google recommends direct, concise instructions without persuasive or emphatic language, ambiguous terms defined, and one structure used consistently.
- Put the role, the constraints and the output format first. Gemini tends toward short answers; if the project needs detailed or conversational ones, say so.

## Consequences for the design
- Knowledge the team edits often can live in Google Drive as Google Docs, as a live source; otherwise Markdown files work as on the other platforms.
- State the web-versus-sources rule in the instructions; it is the main behavior that differs between the two apps.
