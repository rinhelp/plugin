---
name: help-center
description: Review a Rinhelp Help Center for Articles that are out of date, repeat each other, disagree or are hard to find, and fix them. Use when asked to review, audit, clean up or reorganize the help center.
---

# Review the Help Center

1. `article_list` shows the Sections and Articles. `article_read` every Article, Drafts included. `source_list` shows the websites Rin also learns from.
2. Check each Article for:
   - **Out of date**: it disagrees with the website. `knowledge_search` its key claims and compare the Pages that come back.
   - **Repeats**: another Article answers the same question.
   - **Disagrees**: another Article says something different about the same thing.
   - **Hard to find**: no Section, the wrong Section, or a title that isn't a question a customer would ask.
   - **Hard to read**: the answer is buried below the first lines.
   - **Forgotten Draft**: a Draft that's ready, or no longer needed.
3. Report the findings to your Member, the ones that would mislead a customer first. For each: the Article, the problem, and the fix with its exact new text.
4. Apply the fixes your Member confirms: `article_update` for text, Section and title; `section_create` or `section_update` for Sections; for a repeat, merge into one Article and `article_unpublish` the other.
5. `widget_preview` a customer question for each changed Article, and show Rin's answer citing it. On Free this spends the Rin trial: ask first, or `knowledge_search` instead.

Done when every Article was read, and each finding is fixed or your Member declined it.

To find what customers ask that the Help Center doesn't answer at all, use the `gaps` skill.
