---
"@klank/sdk": minor
---

Add public `MessageFilesUpdatedEvent` and `PongEvent` types to `ServerEvent` and refresh the canonical wire fixture. Typed consumers can register `message.files_updated` and `pong` handlers without changing existing bot APIs or heartbeat behavior.

The attachment-completion event carries `channel_id` and `message_id`, is scoped to channel membership, and is emitted only after non-thumbnail attachment persistence; consumers should re-read attachments. The application-level `pong` reply carries no channel context and goes only to the originating socket. Older servers may not emit these events; this change does not claim they are already released.
