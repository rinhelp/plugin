---
name: migrate
description: Move a help desk to Rinhelp from Zendesk, Help Scout, Intercom, Front, Gorgias or another help desk, with its help center, saved replies, past conversations and files. Use when asked to migrate, switch or import from another help desk.
---

# Move to Rinhelp

1. Read the procedure at `https://mcp.rinhelp.com/migrate.md` and follow it step by step. Where it says "the old help desk", read the help desk your Member is leaving. In Claude, the `migrate` prompt gives the same procedure with its name filled in.
2. Read that help desk's page, which holds its limits and traps: `https://rinhelp.com/migrate/<id>.md`, where the id is its name in lowercase with hyphens, such as `help-scout`. If no page answers, find it on https://rinhelp.com/migrate.

Never call `conversation_reply` while importing: it emails the customer.
