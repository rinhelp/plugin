# Switch-over

Ask your Member before each change: these move where customers reach them.

- **Teammates:** `team_list`, then `team_invite` each teammate who still works there. Each gets an email.
- **Email:** `email_show`, then `email_set_address`, or `email_domain_set` and `email_domain_verify` for their own domain. Then your Member forwards the old help desk's support address to the workspace's address. `email_test` checks it.
- **Chat widget:** `widget_update` with their websites, then `widget_show` for the snippet that replaces the old help desk's chat on their website.
- **Old help center links:** if the old help desk's help center had its own domain, `help_center_domain_add` it and give your Member the records to set.
