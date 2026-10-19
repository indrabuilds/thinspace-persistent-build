# Thinspace Persistent — 1.2.2 custom build 20261019

Updated from upstream 0ssamaak0/Thinspace at `9a2ab018a8656c5a086b375de07b553484dba954`.

- Keep Chat Bar Visible restored, enabled by default. Option+Space still explicitly hides/shows.
- Ordinary hidden sessions remain loaded for two hours instead of fifteen minutes.
- Detected Temporary/private Chats are exempt from automatic idle unloading while the app runs.
- Native drag/expand controls sit in their own header above the webpage, leaving Work and other webpage buttons clickable.
- Command+Shift+N retains the existing Temporary Chat handler.

This does not preserve a session across quitting, provider switches, manual reload/navigation, website session expiry, or macOS/WebKit process termination. No private conversations are saved to disk and no artificial keep-alive requests are sent.

Run the manually triggered Build Thinspace Persistent workflow. It applies the patch to pinned upstream, builds, tests, ad-hoc signs, and uploads Thinspace-Persistent-1.2.2.zip. Build artifacts are retained for thirty days. The repository contains only the open-source patch, workflow, and instructions; no accounts or sessions.

Original Thinspace: https://github.com/0ssamaak0/Thinspace
Original attribution and LICENSE are preserved in the build package. Noncommercial adaptation.
