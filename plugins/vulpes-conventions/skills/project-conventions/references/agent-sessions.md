# Agent sessions

These rules apply when an agent session sends a message to another agent session, for example with the `SendMessage` tool of Claude Code.

## Message ID

1. Start the first line of each message with an ID in square brackets: `[<sender>-<id>]`.\
   `<sender>` is a short name of the session that sends the message, for example `infra`.\
   `<id>` is 6 random hexadecimal digits, for example from `openssl rand -hex 3`.\
   Example: `[infra-3f9a1c]`.
2. The ID is an idempotency key.\
   When you send a message again because you do not know that it arrived, use the same ID.
3. When a message arrives with an ID that you saw before, do not do its work again.

## Receipt

1. Send an ACK only when the sender cannot see that the message arrived.\
   A remote session, for example a Remote Control session or a cloud session, does not tell the sender that a message arrived.\
   A local session on the same machine does, so do not send it an ACK.
2. Find the kind of session from the address of the sender.\
   In Claude Code, a `bridge:` address is a remote session, and a `uds:` address is a local session.
3. Write the ACK as one line, `ACK <sender>-<id>`, and send it as soon as the message arrives, before you do the work.
4. Send the ACK only to the session that sent the message.
5. Do not send an ACK for an ACK.
6. When a message with an ID that you saw before arrives again, send the ACK again.
7. When you send a message to a remote session and no ACK comes, send the message again with the same ID.
