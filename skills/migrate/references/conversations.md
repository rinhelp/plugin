# Past conversations

Go from the oldest conversation to the newest, 50 conversations a `conversation_import` call. For each one:

- `contact`: the customer's email and name. Contacts are matched by email.
- `status`: `closed` once solved, closed or archived, else `open`, pending, on hold and snoozed included. Don't send spam or trash. Keep `subject`, `tags`, and `priority` as `urgent` or `normal`.
- Each message: `role` `contact` for the customer, `member` for a teammate or the old help desk's AI, with `authorName` their name; `note: true` for an internal note; `createdAt`; and `body` in Markdown, turned from HTML.

Files never pass through you:

- Call `attachment_upload_link`. Its link works for 60 minutes: get a new one before `expiresAt`.
- Stream each file from the old help desk into it with one shell command, such as `set -o pipefail; curl -sfH "Authorization: Bearer $TOKEN" "$src" | curl -sfT - --url-query "name=$name" -H "Content-Type: $type" "$link"`. It answers `{"id": "..."}`: list the ids in that message's `attachments`. `--url-query` needs curl 7.87 or newer; with an older curl, URL-encode the name into `?name=` yourself. If the command fails, don't use its id: fix the cause and try the file again.
- Take inline images out of the body and upload them as attachments too. When a message was only files, leave its body empty.
- A file over 50 MB can't come: skip it and note its conversation, name and size for the report. Skip a message it leaves with neither text nor files.

Upload a batch's files, then import the batch. Report progress every few batches, and at the end the conversations, messages and files that came in, and the files that were too big.
