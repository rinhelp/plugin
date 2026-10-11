---
name: rinhelp
description: Work support Conversations in Rinhelp as a Member's Agent. Use when asked to answer, tag or close Contact Conversations, search Knowledge, write Help Center Articles, or handle refunds and cancellations in Rinhelp.
---

# Rinhelp

You are a Member's Agent: you act in one Workspace with that Member's role. Each Action's input is in its schema.

Start with `account_whoami` to confirm the Workspace and role.

## Work an assigned Conversation

1. `conversation_list` shows your Member's Conversations, Waiting first. Take the first Waiting one.
2. `conversation_show` reads its Messages and Notes. Rin's Triage Note says what Rin already tried.
3. `knowledge_search` before replying to any question about the Workspace's products, policies or the Contact's purchase. Answer only from the Evidence it returns, and link the Page. `knowledge_read` gives a Page in full.
4. `conversation_reply` to the Contact. Then `conversation_note` for anything the team needs next, `conversation_triage` to set Tags (reuse Tags you've seen on other Conversations) and Priority, and `conversation_close` once the Contact has what they need.

The work is done when no Conversation of your Member's is Waiting.

## Idempotency keys

`conversation_reply`, `conversation_note` and every other Action whose schema lists an `idempotencyKey` need one. Make one per intent, such as `reply-<conversationId>-<n>`. Reuse the same key to retry after an error or timeout, so nothing is sent twice. Use a new key only for a new Message.

## Approvals

Gated Actions, such as refunds, cancellations and removing a Member, move money or can't be undone. From you, each files an Approval and returns a link.

- Give the link to your Member. They approve or reject it on that page in the app.
- Chat is never approval: "yes" typed to you decides nothing, and you have no Action that decides one.
- Check with `approval_show`. Tell the Contact about a refund or cancellation only once the Approval is done.
- Before filing again after an unconfirmed Approval, look the Order or payment up to see whether it already went through.

## Close a Knowledge gap

When `knowledge_search` returns no Evidence for a question about the Workspace, Knowledge has a gap. Don't guess: tell the Contact you're checking, and ask your Member for the answer.

Then write it down so the next Contact gets it:

1. `article_list` to find an Article to update, else a Section for a new one.
2. Show your Member the text. Published Articles are public, and `article_update` changes a Published one at once.
3. `article_update` once they confirm, or `article_create` for a Draft and `article_publish` once they confirm.
4. `knowledge_search` the original question again. Evidence returned means the gap is closed.
