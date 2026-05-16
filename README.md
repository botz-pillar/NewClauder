# Claude Code Tour

**A friendly, no-jargon onboarding tour for people brand-new to Claude Code.**

If you work in IT or security, just installed Claude Code (or are about to), and you're staring at a blank chat wondering *"okay… what now?"* — this is for you. The tour shows you the shape of the tool, gets you to your first real win, and leaves you with a cheat-sheet of things to try tomorrow.

No prior experience with the terminal, GitHub, Python, or AI tools is assumed. You need to be able to type and read. That's it.

---

## Is this for you?

Check any of these:

- [ ] You just installed Claude Code (or are about to) and don't know where to start
- [ ] You work in IT, security, compliance, or somewhere adjacent
- [ ] You've heard "AI agents are a big deal" but every tutorial assumes you're already a developer
- [ ] You're worried about pasting the wrong thing into the wrong tool and breaking something

If any of those hit — keep reading. This is built for you.

If you're a seasoned developer who just wants to know how to configure a hook or wire up an MCP server — skip this. Read the [official Claude Code docs](https://docs.claude.com/en/docs/claude-code/overview) instead. The tour will refuse to run for you anyway.

---

## Before you install anything

A 30-second check, especially if you work in IT or security:

- **On a work laptop?** Many companies have a vendor-approval process for AI tools. Check with your IT/security team before installing. Don't bypass it — getting permission once is cheaper than getting caught.
- **Got sensitive data on your machine** (client files, PHI, classified material)? Same answer.
- **Personal machine, learning purposes?** You're fine. Keep going.

This tool talks to Anthropic when you chat with it. Your conversations are governed by [Anthropic's terms](https://www.anthropic.com/legal/consumer-terms) and the [Trust Center](https://trust.anthropic.com/). By default, your conversations are *not* used to train Anthropic's models. If your org needs zero-retention guarantees, ask them about an enterprise agreement.

---

## Step 1 — Get Claude Code on your machine

You have two paths. **Pick the desktop app unless you already know what a terminal is.**

### The easy path: desktop app

1. Go to **[claude.com/claude-code](https://claude.com/claude-code)**
2. Download the app for your operating system (macOS or Windows)
3. Install it like any other app
4. Open it and sign in with your Anthropic account
5. You'll see a chat window. **You are now inside Claude Code.** That's it.

If anyone tells you that you "need npm" or "need to install Node" — ignore them. That's only for the terminal version. The desktop app needs nothing else.

### The terminal path (skip unless you live in a terminal)

If you're already a terminal user:

```bash
npm install -g @anthropic-ai/claude-code
```

This requires Node.js. On a Mac, easiest install: `brew install node` first. Then run `claude` in any terminal.

If "Node," "npm," or "brew" don't mean anything to you — close this section and use the desktop app instead.

---

## Step 2 — Install this tour

Inside Claude Code, type the following two lines, one at a time, hitting Enter after each:

```
/plugin marketplace add botz-pillar/claude-code-tour
```

```
/plugin install claude-code-tour@claude-code-tour
```

That's the whole installation. The first line tells Claude Code where to find this plugin. The second line installs it.

**What you should see:** after the second command, Claude will confirm it installed the plugin. If something fails, jump to [Troubleshooting](#troubleshooting) below.

---

## Step 3 — Start the tour

Type any of these into the chat (just one — pick whichever sounds like you):

- `I'm new to Claude Code, walk me through it`
- `I'm a SOC analyst, just installed Claude Code — what should I do?`
- `I work in compliance and my boss told me to look at Claude Code. Is this for me?`
- `I'm a helpdesk guy trying to break into security — help me get started`
- `Teach me Claude Code`

The tour will pick up from there. It'll ask you two questions (your job, your terminal comfort), give you the safety story, and then walk you through doing **one real thing** — chosen for your actual role. By the end of the chat you'll have a file you made, a starter-prompts cheat sheet, and a sense of what to try next.

Default tour length: **5 minutes**. Ask for the "full tour" if you want all the concepts.

---

## Where am I? (the most common confusion)

Newcomers get tangled up between three different ways to talk to Claude. Quick reference:

| If you're here… | What you can do | What this tour applies to |
|---|---|---|
| **Claude Code — desktop app** | Chat, read files, edit files, run commands. Slash commands work. | ✅ Yes |
| **Claude Code — terminal** (`claude` command) | Same as desktop. Slash commands work. | ✅ Yes |
| **Claude Code — VS Code / JetBrains extension** | Same as desktop, embedded in your editor. | ✅ Yes |
| **claude.ai in a browser** | Chat only. No files. No slash commands. | ❌ No — different product |
| **Claude iPhone/Android app** | Chat only. | ❌ No |

**The decisive test:** type `/help`. If you see a menu, you're in Claude Code. If `/help` does nothing, you're somewhere else.

---

## What you'll learn

By the end of the tour you'll understand, *in plain English*:

- **Sessions** — what's remembered, what isn't
- **Tools** — what Claude can do on your computer
- **Permissions** — how to keep yourself safe (and a read-only mode for when you're nervous)
- **Folders & projects** — how Claude thinks about your files
- **Slash commands** — typed shortcuts like `/help` and `/clear`
- **Skills** — packaged know-how that activates automatically (like this tour!)
- **MCP servers** — how Claude connects to GitHub, Notion, Splunk, etc.
- **Subagents** — focused helpers for big jobs
- **`CLAUDE.md`** — the file that teaches Claude about your project

You'll learn the names *while you use them*, not as a lecture upfront.

---

## What you do NOT need to learn first

Things people *think* they need to know but absolutely don't:

- The terminal / command line
- Git or GitHub
- Python or any programming language
- Docker
- Regular expressions
- "AI prompt engineering"

You can pick those up later, on demand, when a real task forces you into them. Day one, you just need to type and read.

---

## Troubleshooting

**"`/plugin marketplace add` says it doesn't know that command."**
→ You're on an older version of Claude Code. Update the app (or run `npm update -g @anthropic-ai/claude-code` for the terminal version), restart, try again.

**"I typed the command and nothing happened."**
→ Check that you're in Claude Code, not claude.ai in a browser. Use the `/help` test above.

**"It installed but the tour won't start."**
→ Try one of the trigger phrases in [Step 3](#step-3--start-the-tour) verbatim — exact words like "I'm new to Claude Code, walk me through it" work best. If still nothing, type `/claude-code-tour` directly to force it.

**"How do I uninstall?"**
→ `/plugin uninstall claude-code-tour`. Nothing else stays on your machine.

**"It crashed / I got a weird error."**
→ Two options. Either [open an issue on GitHub](https://github.com/botz-pillar/claude-code-tour/issues) (you'll need a free GitHub account — sign up at [github.com](https://github.com)), **or email me directly** at josh@pillarsecurity.io with the error and what you were doing. Email is fine — you don't need GitHub for this.

---

## Privacy

- **This plugin does not phone home.** It's a folder of instructions Claude reads when you start the tour. No analytics, no telemetry.
- **Your conversation with Claude is governed by Anthropic's terms.** See the [Trust Center](https://trust.anthropic.com/) for data handling, retention, and (for orgs) zero-retention agreements.
- **The tour writes one memory note** at the end — your role, your terminal comfort, and what you built. No conversation content. You can delete it any time from `~/.claude/memory/user_claude_code_onboarding.md`.

---

## License

MIT. See [LICENSE](./LICENSE).

## Who made this

[Josh Botz](https://github.com/botz-pillar) — cloud security practitioner, builder of [AI Cloud Security Lab](https://aicloudsecuritylab.com), occasional writer of skills like this one.

If this helped you, the kindest thing you can do is tell one other person in IT or security who's struggling to get started with AI tools. That's it. No stars required (but they're nice).

## Feedback

- **Found a bug or have an idea?** [Open a GitHub issue](https://github.com/botz-pillar/claude-code-tour/issues).
- **Never used GitHub before?** Email josh@pillarsecurity.io — happy to hear it.
- **Want to share what you built during the tour?** Same email. I love seeing first-day artifacts.
