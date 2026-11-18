---
name: migrate
description: Move a help desk to Rinhelp from Zendesk, Help Scout, Intercom, Front, Gorgias or another help desk, with its help center, saved replies, past conversations and files. Use when asked to migrate, switch or import from another help desk.
---

# Move to Rinhelp

You are moving your Member's help desk from the old help desk to Rinhelp. Do the steps in order. Before each step, say what it will do; after it, report what it did. Read a step's reference file only when you reach that step.

## Rules for the whole move

- Only an owner can import. If `account_whoami` doesn't say `owner`, stop and ask your Member to connect an owner's AI agent.
- Never call `conversation_reply` while importing: it emails the customer. Past conversations come in only through `conversation_import`, which emails nobody, never runs Rin and never counts toward a plan.
- Every import call takes the same `source`: the old help desk's name in lowercase with no spaces, such as `zendesk` or `helpscout`. Articles and conversations are keyed by `source` and their ID in the old help desk, and saved replies by name, so sending a batch again is safe. After an error or a timeout, send the same batch again.
- Rinhelp runs 60 actions a minute for your agent. When an action says to try again shortly, wait a minute and send it again.
- Read the old help desk through its API with access your Member sets up there. Zendesk no longer issues new API tokens, so use OAuth for it. Keep the token in an environment variable on their machine, and never pass it to a Rinhelp action.
- If you can write files, keep a progress file of the old IDs each step finished, so you can resume where you stopped.

## Steps

1. **Inventory and time estimate.** Count, in the old help desk: help center articles and sections in the default language, saved replies (also called macros, templates or canned responses), conversations, files, teammates, the support email address, and the websites that show its chat widget. Rinhelp takes 25 articles, 50 saved replies or 50 conversations a call, so 1,500 articles or 3,000 conversations a minute. The old help desk's own API limit is usually slower: estimate from its requests a minute, plus the time to download the files. Show your Member the counts and the estimate, and ask before you start.
2. **Help center.** Read `references/help-center.md`.
3. **Saved replies.** Read `references/saved-replies.md`.
4. **Website.** Ask your Member for their website, and add it with `source_add` so Rin learns from it.
5. **Past conversations.** Only in a coding agent with a shell, such as Claude Code, Codex or Cursor: read `references/conversations.md`. In a chat app, skip it and tell your Member to run steps 5 and 7 in a coding agent.
6. **Switch-over.** Read `references/switch-over.md`.
7. **Catch-up.** Only in a coding agent. Once email and chat come to Rinhelp, run step 5 again for the conversations updated in the old help desk since step 5 began. Only new messages are added, so upload files only for messages newer than your last import. Then tell your Member the move is done, with everything that was skipped or dropped.
