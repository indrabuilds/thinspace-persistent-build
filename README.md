# Thinspace — edge-to-edge with idle-error recovery

Custom build 2026102801, based on Thinspace 1.2.2 at 9a2ab018a8656c5a086b375de07b553484dba954.

After at least one hour without activity, a visible ChatGPT page is eligible for
one controlled recovery only when WritingBlockInvalidConversationError persists.
Healthy pages remain untouched. Replies, recent edits, composition, unknown private
mode, and detected attachments block recovery. Draft text is protected in memory,
never automatically submitted, and restored only after confirming private mode for
private drafts. If the temporary page cannot resume, a fresh Temporary Chat may
open and a brief notice explains that the session changed. A retry budget prevents
loops. Copy Recovered Draft appears in the menu only if automatic restoration fails.

No private draft is saved to disk, sent as a keep-alive, or placed on the clipboard
without the user's Copy action. The one-hour checkpoint is an engineering choice,
not a claim about OpenAI's session expiry. Recovery depends on the live website DOM;
unknown or unsupported states are left alone. Website or account sign-in expiry may
still require user action. Quitting loses memory-only backup text.

The rimless layout, persistent bar, Option+Space, Command+Shift+N, Command+Option-drag,
Command+Shift+Return, ordinary two-hour hidden retention, and Temporary Chat idle-unload
exemption are retained. Original project: https://github.com/0ssamaak0/Thinspace
Original attribution and LICENSE are preserved. Noncommercial adaptation.
