# Install / pre-flight reference

Only use this if the user says they have not installed Claude Code yet, or seems unsure whether it's running on their machine.

If they are already chatting with you in Claude Code, they are already inside it — say so explicitly: **"You're talking to me through Claude Code right now. It's already installed and running. We're good to go."** Then return to Step 1 of the tour.

---

## If they genuinely haven't installed yet

Ask which OS: **macOS, Windows, or Linux.**

### macOS

Two ways:

1. **The app** — download the Claude Code desktop app from `claude.com/claude-code`. Easiest path for non-CLI users. Open it, sign in, you're in.
2. **The CLI** — if they want the terminal version:
   ```
   npm install -g @anthropic-ai/claude-code
   ```
   This needs Node.js installed (which gives them `npm`). Easiest install is via Homebrew:
   ```
   brew install node
   ```
   Then run `claude` in any terminal.

If they don't have Homebrew, that's a longer detour — link them to `brew.sh` and offer to walk through it, but suggest the desktop app instead if they're not committed to the CLI path.

### Windows

The desktop app is the path of least resistance — same URL.

If they want the CLI, recommend WSL (Windows Subsystem for Linux) + Node, but flag that as a "set aside an hour" project. For a new user, the app is fine.

### Linux

`npm install -g @anthropic-ai/claude-code` after Node is installed via their distro's package manager (apt, dnf, pacman).

---

## Confirming it worked

After install, they should be able to:

1. Open the app (or run `claude` in a terminal).
2. Sign in with their Anthropic account.
3. See a chat prompt waiting for input.

If any of those don't happen, ask what they see and troubleshoot from there.

---

## Should they even install it?

A fair question for some users. Quick sanity check:

- **Work laptop with strict controls?** Check with IT/security before installing anything that calls outbound to Anthropic. Many orgs have a vendor-approval process. Don't bypass it.
- **Sensitive data on the machine?** Same answer.
- **Personal machine, learning purposes?** Go for it. The desktop app is the safest starting point.

---

## What "you're already inside it" looks like

If you (Claude) are reading this skill, the user is talking to you through Claude Code. They are inside the tool. They might not realize this. A single sentence — "you're already in Claude Code; this chat IS the tool" — saves them ten minutes of confusion.
