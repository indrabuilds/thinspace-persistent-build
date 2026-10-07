# Build Thinspace without local Xcode

This package contains a manually triggered GitHub Actions workflow plus the
persistent Chat Bar patch. It clones Thinspace at the exact upstream commit,
applies the patch, builds on GitHub's Apple silicon `xcode-27` preview runner,
runs ThinspaceTests, ad-hoc signs the app, and uploads a ZIP if all steps pass.
It has not been submitted to GitHub or executed yet.

## Run through GitHub's website

1. Sign in to GitHub and create an empty repository. A public repository uses
   GitHub's free standard hosted runners. A private repository uses your account's
   included Actions minutes and may incur charges beyond those minutes.
2. Upload `thinspace-persistent-chat-bar.patch` to the repository root.
3. Create a file named `.github/workflows/build-thinspace.yml` using GitHub's
   Add file → Create new file control. Paste the contents of the supplied YAML
   file and commit it to the default branch. Hidden folders are sometimes omitted
   by web uploads, so creating this file explicitly avoids that problem.
4. Open Actions → Build Thinspace Persistent → Run workflow.
5. Wait for success, then download `Thinspace-Persistent-macOS-arm64` from the
   run's Artifacts section. If it fails, download the diagnostics or inspect the
   failed step; no successful build is assumed before this finishes.
6. Extract the artifact, then extract its `Thinspace-Persistent.zip`.
7. Quit existing Thinspace instances. Rename the extracted app to
   `Thinspace Persistent.app`, drag it into Applications, and open it.
8. Because this is an ad-hoc signed build, macOS may require approval through
   System Settings → Privacy & Security → Open Anyway. It is not notarized.
9. Leave Settings → Chat Bar → Keep Chat Bar Visible enabled, then test Finder
   drag-and-drop, Option+Space show/hide, and Command+Shift+N Temporary Chat.

No Apple Developer certificate, ChatGPT login, or account secret is uploaded.
The build runner compiles the app; use your ChatGPT account only after installing
it on your own Mac. A CI build does not verify interactive ChatGPT file uploads.

Thinspace upstream: https://github.com/0ssamaak0/Thinspace
Base: eefd70060f8492d98b77e62550efebd3ab64f5b4
Changes: persistent Chat Bar setting, default on, with legacy dismissal available.
Upstream attribution and LICENSE are retained. Noncommercial adaptation.

Runner documentation:
https://docs.github.com/en/actions/reference/runners/github-hosted-runners
https://github.com/actions/runner-images/blob/main/images/macos/xcode-27-arm64-Readme.md
