# Help center

Send articles to `article_import`, 25 a call, in the old help desk's order, section by section, in its default language only.

- Each top-level category or collection becomes a section: put its name in `section`. Fold deeper levels into their top-level section.
- Turn each article's HTML into Markdown for `body`. Keep images as Markdown images with their full address: Rinhelp copies them. Report any `imagesNotCopied`.
- Set `url` to the article's old public address, so old links lead to the new article once the old help center's domain points to Rinhelp (switch-over).
- Set `published` to false for drafts, and keep `createdAt` and `updatedAt`.

Then `help_center_show` and give your Member the new help center's address.
