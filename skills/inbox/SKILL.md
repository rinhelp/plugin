---
name: inbox
description: Answer the customer conversations waiting in Rinhelp. Use when asked to work, clear or check the Rinhelp inbox, or when a Rinhelp webhook says conversations are waiting.
---

# Inbox

Work every Conversation where your Member owes the next reply: the Waiting ones.

1. `conversation_list` lists your Member's Conversations, Waiting first. Take the first Waiting one.
2. `conversation_show` reads its Messages and Notes. Rin's Triage Note says what Rin already tried, and the Starting Article is the page the Contact was reading.
3. Look up what the reply needs: `knowledge_search` for products and policies (`knowledge_read` gives a Page in full), and the Integration's find Action, such as `shopify_order_find`, for an Order or payment.
4. `conversation_reply` to the Contact. Then `conversation_note` for anything the team needs next, `conversation_triage` for Tags (reuse the Workspace's Tags) and Priority, and `conversation_close` once the Contact has what they need.
5. Repeat until `conversation_list` shows nothing Waiting.

When Knowledge has no answer, tell the Contact you're checking and ask your Member. Once they answer, reply, then offer to run the `gaps` skill so Rin answers it next time.

When nobody is in the chat to ask, such as a run started by a webhook, reply only from Evidence. For anything else, leave a Note with the question for your Member and leave the Conversation Waiting.

Finish with a short report: what you replied to, what you closed, and what still waits on your Member, with each Approval link and question.
