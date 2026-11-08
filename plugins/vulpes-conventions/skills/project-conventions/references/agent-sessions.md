# Agent sessions

These rules apply when an agent session sends a message to another agent session, for example with the `SendMessage` tool of Claude Code.

## Message ID

1. Start the first line of each message, but an ACK, with an ID in square brackets: `[<sender>-<id>]`.\
   `<sender>` is a short name of the session that sends the message, for example `infra`.\
   Use a sender name that no other session uses at the same time.\
   `<id>` is 6 random hexadecimal digits, for example from `openssl rand -hex 3`.\
   Example: `[infra-3f9a1c]`.
2. Make a new ID for each new message.\
   If the new ID is an ID that you used before, make a different one.
3. The ID is an idempotency key.\
   When you send a message again because you do not know that it arrived, use the same ID.
4. Keep the IDs of the messages that you received, with their content, for the life of the session.\
   When a message arrives with an ID and content that you received before, do not do its work again.
5. When a message arrives with an ID that you received before, but with different content, it is a new message.\
   Do its work, and tell the sender that the ID was used two times.

## Receipt

1. Send an ACK only when the sender cannot see that the message arrived.\
   A remote session, for example a Remote Control session or a cloud session, does not tell the sender that a message arrived.\
   A local session on the same machine does, so do not send it an ACK.
2. Find the kind of session from the address of the sender.\
   In Claude Code, a `bridge:` address is a remote session, and a `uds:` address is a local session.
3. An ACK has no ID of its own.\
   Write it as one line, `ACK <sender>-<id>`, with the full ID of the message, for example `ACK infra-3f9a1c`.
4. Send the ACK as soon as the message arrives, before you do the work.
5. Send the ACK only to the session that sent the message.
6. Do not send an ACK for an ACK.
7. When a message arrives again with an ID and content that you received before, send the ACK again if rule 1 requires an ACK for it.

## Resend

These rules apply to all messages except an ACK.

1. When you send a message to a remote session, wait for its ACK.
2. When no ACK comes in 10 minutes, send the message again with the same ID.
3. Send the message again 2 times at most.\
   When no ACK comes in 10 minutes after the last send, stop, and tell the user that the message possibly did not arrive.
