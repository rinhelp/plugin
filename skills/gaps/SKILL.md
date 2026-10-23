---
name: gaps
description: Close Rinhelp Knowledge gaps, the customer questions Rin couldn't answer, by writing Help Center Articles and proving Rin now answers. Use when asked to improve the help center, fill gaps, or find what customers ask that Rin can't answer.
---

# Close Knowledge gaps

Rin tags a Conversation "Knowledge gap" when a Contact asks something Knowledge doesn't cover. Turn each gap into an Article, then prove Rin answers it.

1. `knowledge_gap_list` gives the questions from the last 30 days, or from the date your Member names.
2. `knowledge_search` each question. Evidence returned means it's already covered: set it aside.
3. Group the rest by the answer they need. One Article answers one topic, and several questions can share it.
4. `article_list` shows the Sections and Articles. For each group, pick an Article to extend, else a Section for a new Article.
5. Find each answer, in this order: Pages `knowledge_search` returns for nearby questions; the user's own files and code, when you can read them; your Member. Every fact comes from one of these. Ask your Member for what none of them gives, and leave that group for later if they don't know.
6. Show your Member the plan: per Article its title, Section, full text and the questions it answers. Title it with the question in the Contact's words, and answer in the first line.
7. Once your Member confirms, `article_update` the Articles you extend, and `article_create` then `article_publish` the new ones.
8. Prove it: `widget_preview` each original question. The gap is the before, so show both: "Before: Rin handed off. Now: Rin answers …, citing …". When Rin still hands off, sharpen the Article and test again.
9. For each gap whose status is open, `conversation_show` it. When the Contact is still Waiting, offer your Member a reply that answers them and links the Article, and send the ones they approve.

Done when every question is covered, with Rin's answer shown, or listed as waiting on an answer from your Member.

## Test Rin costs

On Free, `widget_preview` spends the Rin trial, so ask your Member before step 8. When it fails, because the trial is used up or the daily limit is reached, `knowledge_search` each question instead and show the Evidence the new Article gives.

## When nobody is in the chat

In a run with nobody to confirm, such as a scheduled task, stop at step 7 with `article_create` alone: the Articles stay Drafts. Finish with each Draft, the questions it answers, and what your Member must check before publishing.

At the end of a run with your Member, offer to schedule this skill weekly.
