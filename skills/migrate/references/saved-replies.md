# Saved replies

List every saved reply in the old help desk, shared and personal.

- Skip the ones with no reply text, which only run actions.
- Drop actions, attachments and subjects: a Rinhelp saved reply is a name and plain text.
- Turn the HTML body into plain text. Write each link as its bare address, and each image as a link to it.
- Replace each placeholder with Rinhelp's. Turn its fallback, such as Help Scout's `,fallback=there`, Front's `| 'there'` or Intercom's `|fallback:"there"`, into `| default: "there"`:

  | Rinhelp | Help Scout | Front | Intercom (`body_text`) | Gorgias | Zendesk |
  | --- | --- | --- | --- | --- | --- |
  | `{{customer.first_name}}` | `{%customer.firstName%}` | `{{recipient.first_name}}` | `{{user.first_name}}` | `{{ticket.customer.firstname}}` | `{{ticket.requester.first_name}}` |
  | `{{customer.name}}` | `{%customer.fullName%}` | `{{recipient.name}}` | `{{user.name}}` | `{{ticket.customer.name}}` | `{{ticket.requester.name}}` |
  | `{{customer.email}}` | `{%customer.email%}` | `{{recipient.email}}` | `{{user.email}}` | `{{ticket.customer.email}}` | `{{ticket.requester.email}}` |
  | `{{teammate.first_name}}` | `{%user.firstName%}` | `{{user.first_name}}` | `{{message.author.first_name}}` | `{{current_user.firstname}}` | `{{current_user.first_name}}`, `{{ticket.assignee.first_name}}` |
  | `{{teammate.name}}` | `{%user.fullName%}` | `{{user.name}}` | `{{message.author.name}}` | `{{current_user.name}}` | `{{current_user.name}}`, `{{ticket.assignee.name}}` |

  `user` means the customer in Intercom but the teammate in Help Scout and Front. Intercom's teammate keys and Gorgias's `{{ticket.customer.name}}` come from their email template docs: check one imported reply. For another help desk, match by meaning. Turn every other placeholder into a bracket a teammate will fill in, such as `[order number]`.
- Fold folders and categories into the name, such as "Billing / Refunds" for Zendesk's "Billing::Refunds".
- List the personal ones for your Member, and import them as shared only if they agree.

Send them to `saved_reply_import`, 50 a call. A name the workspace already has is skipped.

Report how many came in; for each one, what was dropped and which placeholders became brackets; how many were skipped, as personal, as action-only or as a name already taken; and that folders became name prefixes.
