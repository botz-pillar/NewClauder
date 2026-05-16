# NewClauder

**Get from install to your first useful Claude Code session in about 15 minutes — even if you've never touched a terminal.**

If you work in IT or security, just heard about Claude Code (or are setting it up for the first time), and you're not sure where to start — this is for you. The tour shows you the shape of the tool, gets you to your first real win, and leaves you with a cheat-sheet of things to try the next day.

**No prior coding experience required.** Not the terminal. Not GitHub. Not Python. Not AI tools. If you can type and read, you can do this. We'll walk you through every step below — start to finish — including signing up for the things you might not have yet.

> **A note about safety first:** because Claude Code can run commands and edit files on your machine, "no prior experience required" applies to *getting set up* — not to *what you let it do*. Sections 2, 3, and 4 below cover the honest version of what that means before you install anything.

---

## Table of contents

1. [Is this for you?](#1-is-this-for-you)
2. [Before you install (work-laptop / sensitive-data check)](#2-before-you-install)
3. [What you'll actually be able to do](#3-what-youll-actually-be-able-to-do)
4. [What this means for your machine (the honest safety version)](#4-what-this-means-for-your-machine)
5. [Cost: Claude Code requires a paid plan](#5-cost-claude-code-requires-a-paid-plan)
6. [Set up your Claude account](#6-set-up-your-claude-account)
7. [Install Claude Code on your computer](#7-install-claude-code-on-your-computer)
8. [Install this tour](#8-install-this-tour)
9. [Start the tour](#9-start-the-tour)
10. ["Wait, where am I?" reference](#10-wait-where-am-i)
11. [What you'll learn (in plain English)](#11-what-youll-learn)
12. [What you do NOT need to learn first](#12-what-you-do-not-need-to-learn-first)
13. [Helpful links for beginners](#13-helpful-links-for-beginners)
14. [Troubleshooting](#troubleshooting)
15. [Privacy](#privacy)
16. [Feedback & contact](#feedback--contact)

---

## 1. Is this for you?

Check any of these:

- [ ] You just installed Claude Code (or are about to) and don't know where to start
- [ ] You work in IT, security, compliance, or somewhere adjacent
- [ ] You've heard "AI agents are a big deal" but every tutorial assumes you're already a developer
- [ ] You're worried about pasting the wrong thing into the wrong tool
- [ ] You don't have a GitHub account or anything special installed and that has been a blocker

Any of those hit? Keep reading.

Already a developer comfortable with the terminal, MCP servers, and hooks? Skip this. Read the [official Claude Code docs](https://docs.claude.com/en/docs/claude-code/overview) instead.

---

## 2. Before you install

**Getting permission once is cheaper than getting caught.** If you're on a work laptop, check with IT/security before installing — most companies now have a vendor-approval process for AI tools, and many run MDM (mobile-device management), DLP (data-loss prevention), or EDR (endpoint-detection) agents that will either block the install or quietly log every file Claude Code reads.

A 30-second check before you touch the installer:

- **Work laptop with corporate management?** Stop. Ask IT/security. Forwarding policy violations is harder than checking first.
- **Sensitive data on your machine** — client files, PHI, regulated material, NDA-protected docs? Same answer.
- **Personal machine + non-sensitive learning projects?** You're good. Continue.
- **Personal machine but the folder you'd open contains any work data?** Treat it like a work laptop.

When you chat with Claude Code, your messages go to Anthropic. Conversations are governed by [Anthropic's Commercial Terms](https://www.anthropic.com/legal/commercial-terms) (for Pro/Max/Team/Enterprise) or [Consumer Terms](https://www.anthropic.com/legal/consumer-terms) (for the free Claude plan, which doesn't include Claude Code anyway — see section 5). By default, Claude Code traffic is **not** used to train Anthropic's models. For zero-retention guarantees, your org needs an enterprise agreement. See the [Trust Center](https://trust.anthropic.com/) for the authoritative details.

---

## 3. What you'll actually be able to do

Concrete, not abstract. By tomorrow morning you could be doing things like:

- **Pasting a suspicious email or alert into the chat** — Claude reads the headers and body, pulls out the indicators, drafts a verdict paragraph you could send back to the reporter, and saves the analysis to a file.
- **Pointing Claude at a folder of logs** — it ranks the noisy IPs, finds the talkers, and outputs a CSV you can hand to the next analyst.
- **Asking it to draft a Sigma rule, Splunk SPL, or KQL query for a CVE you just read** — and lint it against your existing rule pack before you commit.
- **Turning a regulator's findings PDF into a tracker** — control, owner, severity, due date, evidence needed.
- **Walking it through a codebase you inherited** — and getting back a `CLAUDE.md` future-you can re-use.

It's a chat where Claude can also touch your files and run commands on your machine — with your approval each time. The tour in section 9 will pick one of these (matched to your role) and do it with you live.

> **Heads up for the tour exercise:** the examples above are *capabilities*, not what you should paste in during your first session. Use **synthetic, sample, or non-sensitive content** for the tour — practice the workflow without putting real client data, PHI, or regulated material through it the first time. The tour will pick low-stakes example data so you can focus on learning the tool.

---

## 4. What this means for your machine

The honest version, in three plain-English sentences:

- **When you approve a Claude Code command, it runs with your user's full permissions** — same as if you typed it yourself in a terminal. Approving `rm -rf` deletes files. Approving a "curl-this-and-pipe-to-bash" runs whatever that script says. Read the proposed command before you say yes.
- **Claude reads file content and web pages as both data AND instructions.** A malicious README, log entry, or webpage can try to redirect Claude into taking actions you didn't ask for — this is called *prompt injection*, and it's the defining new risk class of agentic AI tools. **The tell:** if Claude proposes an action that doesn't match what you originally asked for after it just read a file or visited a URL, that's the signature of an injection attempt — stop and check before approving.
- **There's a read-only mode for when you're nervous.** Type `/permissions` inside Claude Code and put it in **plan mode** — it can look at things and propose ideas but can't change anything until you flip it back. Recommended for your first session and any session pointed at unfamiliar data.

You don't need to memorize this. The tour will hand it back to you at the moment it matters. Plan mode is also covered in the concept list in section 11.

---

## 5. Cost: Claude Code requires a paid plan

Disclosing this **before** you create an account, because it matters: Claude Code does **not** work on the free Claude plan. You'll need one of these:

- **[Claude Pro](https://www.anthropic.com/pricing)** — about **$20/month**. **Start here.** Enough usage for learning, light/moderate daily use, and most personal projects. You can upgrade later.
- **[Claude Max](https://www.anthropic.com/pricing)** — tiered, starting around **$100/month**. For people using Claude Code as a daily driver. Substantially higher limits.
- **[Anthropic API credits](https://console.anthropic.com/)** — pay-as-you-go. Useful if you want to meter usage by tokens rather than commit to a subscription. Skip unless you already know you prefer this model.

**Whether it's worth the cost is a personal call.** Some folks save five-plus hours a week and the math is obvious; others try it for a month and decide it's not for them yet. Both are valid.

> **Want to feel out the vibe before paying?** Try the free chat at [claude.ai](https://claude.ai) for a few days — ask it actual questions from your job and see how it thinks. The free plan won't run Claude Code (the agent on your machine), but it's the same brain. If you like the conversation, the paid plan unlocks the hands.

The rest of this README assumes you've decided to try it.

---

## 6. Set up your Claude account

1. Go to **[claude.ai/signup](https://claude.ai/signup)**
2. Sign up with email, Google, or Apple
3. Subscribe to **[Claude Pro](https://www.anthropic.com/pricing)** (per section 5)

> **Sidebar — "what's the difference between Claude and Claude Code?"**
> *Claude* is the AI chat at claude.ai. *Claude Code* is the same AI with the ability to read files, run commands, and edit things on your computer — only after each action you approve. Same account, same subscription. This tour is for Claude Code.

---

## 7. Install Claude Code on your computer

You have two paths. **Pick the desktop app unless you already use the terminal regularly.**

### Path A — Desktop app (recommended for most people)

1. Go to **[claude.com/claude-code](https://claude.com/claude-code)**
2. Download the app for your operating system (macOS or Windows)
3. Install it — double-click the download on Mac, run the installer on Windows
4. Open the app and sign in with the Anthropic account you just made
5. You'll see a chat window — this is Claude Code, *not* the browser chat you used in section 6

> **Heads up if you're on a managed machine:** the installer may need admin rights. If your laptop is locked down by IT, the install will halt with a credentials prompt. Don't enter someone else's credentials — go back to section 2 and check policy first.

### Path B — Terminal (only if you're already a terminal user)

```bash
npm install -g @anthropic-ai/claude-code
```

Requires Node.js.

- **macOS:** `brew install node` first (or download from [nodejs.org](https://nodejs.org/)). Then run `claude` in any terminal.
- **Windows:** install Node via [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/) (`winget install OpenJS.NodeJS`) or download from [nodejs.org](https://nodejs.org/). Then run `claude` in PowerShell or Windows Terminal.
- **Linux:** install Node from your distro's package manager (`apt`, `dnf`, `pacman`). Then run `claude` in any terminal.

If "Node," "npm," or "winget/brew" don't mean anything to you — go back to Path A. Same product. No downside.

### Confirm Claude Code is working

After installing, you should:

1. See a chat window with a text input at the bottom — *inside the Claude Code app you just installed, not the browser chat at claude.ai*
2. Be signed in
3. Be able to type `/help` and see a menu of commands pop up

If `/help` does nothing or just prints `/help` as text, you're probably in the wrong place — the browser chat at claude.ai doesn't support slash commands. Open the Claude Code app. See section 10 for the full "which surface am I in?" reference if you're still confused.

---

## 8. Install this tour

Before you install: this plugin is a folder of plain markdown instructions plus a couple of supporting reference files. It makes no network calls, adds no tools to Claude Code, and requests no additional permissions. The source is at [github.com/botz-pillar/NewClauder](https://github.com/botz-pillar/NewClauder) — every file is human-readable.

> **Standing rule for any Claude Code plugin: read it before you install it.** This plugin's source is public and every file is plain markdown. The same discipline applies to *every* plugin you'll consider going forward — third-party plugins can install tools, request permissions, or include scripts. Trust nothing you can't read. This is the single most valuable security habit for working with an agentic AI tool.

Two commands. **Run them one at a time.** Type the first, press Enter, wait for the confirmation message, *then* type the second.

### First command — type this, then press Enter:

```
/plugin marketplace add botz-pillar/NewClauder
```

**You should see something like:** *"Marketplace 'new-clauder' added."* If you see anything else — an error, a red warning, nothing at all — copy the message and paste it back to Claude with *"what does this mean?"* — Claude is excellent at decoding its own errors.

---

### *Wait for that confirmation. Then* — type the second command:

```
/plugin install new-clauder@new-clauder
```

**You should see:** a confirmation that the plugin is installed, possibly with an approval prompt — say yes. The tour is now installed.

> If you accidentally paste both lines at once you'll get *"is not a valid repository name."* No harm done — re-run them one at a time. Welcome to slash-command quirks.

---

## 9. Start the tour

In the same chat (or a new one), type **any one** of these:

- `I'm new to Claude Code, walk me through it`
- `I'm a helpdesk guy trying to break into security — help me get started`
- `I work in compliance and my boss told me to look at Claude Code. Is this for me?`

The tour will ask you two questions (your day job, your terminal comfort), give you the safety story, then walk you through **one real thing** chosen for your role. By the end of the chat you'll have a file you made, a starter-prompts cheat sheet saved to your Documents folder, and a sense of what to try next.

Default tour length: **5–10 minutes**, depending on how deep your role-matched exercise goes. Ask for the *"full tour"* if you want all the concepts walked through explicitly.

> **Magic phrase for any moment you're overwhelmed:**
> Type *"slow down and explain like I'm new"* — the tour will reset its pace and walk you through whatever confused you. Use it freely; it's literally what the phrase is for.

---

## 10. "Wait, where am I?"

Reference for surface confusion. Newcomers get tangled up between the different places "Claude" lives:

| If you're here… | What you can do | Does this tour work here? |
|---|---|---|
| **Claude Code — desktop app** | Chat, read your files, edit files, run commands. Slash commands work. | ✅ Yes |
| **Claude Code — terminal** (`claude` command) | Same as desktop. Slash commands work. | ✅ Yes |
| **Claude Code — VS Code or JetBrains extension** | Same as desktop, embedded in your editor. | ✅ Yes |
| **claude.ai in a web browser** | Chat only. No files. No slash commands. | ❌ No — different product |
| **Claude iPhone/Android app** | Chat only. | ❌ No |

**The decisive test:** type `/help`. If you see a menu, you're in Claude Code. If `/help` does nothing or just shows up as text, you're somewhere else.

---

## 11. What you'll learn

By the end of the tour you'll understand — *in plain English*:

- **Sessions** — your conversation; what's remembered between turns and what gets summarized
- **Tools** — the verbs Claude can use on your machine (read, write, run, search)
- **Permissions** — the approve-before-acting system (and the read-only **plan mode** from section 4)
- **Folders & projects** — Claude works on one folder at a time; opening another folder is how you switch projects
- **Slash commands** — typed shortcuts like `/help`, `/clear`, `/permissions`
- **Skills** — packaged know-how that activates automatically based on what you ask (like this tour)
- **MCP servers** — external systems Claude can plug into (GitHub, Notion, Splunk, etc.) — each one is its own trust decision, the same way every plugin is
- **Subagents** — focused helpers for big jobs that would clog the main chat
- **`CLAUDE.md`** — a file in your project that teaches Claude its conventions and gotchas

You'll learn the names *while you use them*, not as a lecture upfront.

---

## 12. What you do NOT need to learn first

Things people *think* they need before starting — they don't:

- The terminal / command line
- Git or GitHub
- Python or any programming language
- Docker
- Regular expressions
- "AI prompt engineering"

Pick those up later, on demand, when a real task forces you into them. Day one, you just need to type and read — *and* read the proposed commands before you approve them (see section 4).

---

## 13. Helpful links for beginners

You don't need any of this for the tour. Bookmark this section for the *day after*, when you start wondering "what's next?"

**Official Claude Code:**
- [Claude Code overview](https://docs.claude.com/en/docs/claude-code/overview) — the official docs
- [Anthropic Trust Center](https://trust.anthropic.com/) — data handling, retention, compliance answers

**A nicer way to read `.md` files** (the tour will save Markdown files to your Documents folder):
- [Obsidian](https://obsidian.md/) — free, most popular Markdown reader
- [VS Code](https://code.visualstudio.com/) — also free, with a built-in Markdown preview (Ctrl/Cmd + Shift + V)

**When you're ready for GitHub** (no rush — needed for the day you want to publish or fork things):
- [github.com/join](https://github.com/join) — free, two minutes
- [GitHub Hello World](https://docs.github.com/en/get-started/start-your-journey/hello-world) — their official first-repo walkthrough

**When you're ready for the terminal** (no rush):
- [The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) — free MIT class on the terminal, shell, and version control. Best resource on the internet for this.

**Free security learning that pairs well with Claude Code:**
- [TryHackMe](https://tryhackme.com/) — hands-on cybersecurity learning; pair it with Claude Code for writing up what you solved
- [Microsoft Learn — Security paths](https://learn.microsoft.com/en-us/training/browse/?roles=security-engineer) — free, well-structured

**Stuck on anything else?** Just ask the Claude chat directly: *"I'm stuck on X — explain like I'm new."* Don't grind silently.

---

## Troubleshooting

**"`/plugin marketplace add` says it doesn't know that command."**
→ You're on an older version of Claude Code. Update the app (or run `npm update -g @anthropic-ai/claude-code` for the terminal version), restart, try again.

**"I typed the command and nothing happened."**
→ Check that you're in Claude Code, not claude.ai in a browser. Use the `/help` test in [section 10](#10-wait-where-am-i).

**"I got an error like 'is not a valid repository name.'"**
→ You pasted both install commands at once. Run them one at a time, with Enter between. See [section 8](#8-install-this-tour).

**"It installed but the tour won't start."**
→ Try one of the trigger phrases in [section 9](#9-start-the-tour) verbatim — exact wording like *"I'm new to Claude Code, walk me through it"* works best. If still nothing, type `/new-clauder` directly to force it.

**"The installer asked for admin rights and I can't proceed."**
→ Your laptop is managed by IT. Go back to [section 2](#2-before-you-install) and check policy. Don't enter someone else's credentials.

**"Some other weird error I can't decode."**
→ Copy the message, paste it into the Claude Code chat, ask *"what does this mean and how do I fix it?"* Claude is good at this. Genuinely.

**"How do I uninstall the tour?"**
→ `/plugin uninstall new-clauder`. Nothing else stays on your machine.

**"Something is broken and the above didn't help."**
→ [Open a GitHub issue](https://github.com/botz-pillar/NewClauder/issues) (need a free GitHub account — see [section 13](#13-helpful-links-for-beginners) if you don't have one yet), or **email josh@pillarsecurity.io** — you don't need GitHub.

---

## Privacy

- **This plugin makes no network calls of its own.** It's a folder of markdown instructions that Claude reads when you start the tour. No analytics, no telemetry, no third-party services. The repo is public at [github.com/botz-pillar/NewClauder](https://github.com/botz-pillar/NewClauder) — every file is readable before you install.
- **Your conversation with Claude is governed by Anthropic's terms.** The plugin doesn't change that — see the [Trust Center](https://trust.anthropic.com/) for data handling, retention, and zero-retention enterprise options.
- **The tour writes one memory note at the end.** Here's exactly what gets written, structurally:

```markdown
---
name: user-claude-code-onboarding
description: User finished the new-clauder onboarding — role, terminal comfort, first artifact produced, suggested next step.
metadata:
  type: user
---

User finished the new-clauder onboarding on <YYYY-MM-DD>.

- **Role:** <SOC / GRC / IT / pentest / helpdesk-to-security / dev / just trying it>
- **Terminal comfort:** <never opened it / sometimes / lives in it>
- **First artifact produced:** <file path + one-line description>
- **Next step they picked:** <one-line summary>
- **Notes for next session:** Greet them warm; reference what they built; offer to keep going on their next step.
```

No conversation content. Delete the file any time from `~/.claude/memory/user_claude_code_onboarding.md`.

---

## Feedback & contact

- **Found a bug or have an idea?** [Open a GitHub issue](https://github.com/botz-pillar/NewClauder/issues).
- **Never used GitHub before?** Email **josh@pillarsecurity.io** — happy to hear it. I read every message and try to reply within a week. If something is broken for you, you're not the only one — write me and I'll fix it.
- **Want to share what you built during the tour?** Same email. I love seeing first-day artifacts.

---

## License

MIT — see [LICENSE](./LICENSE). Use it, fork it, share it, remix it for your org.

## Who made this

[Josh Botz](https://github.com/botz-pillar) — cloud security practitioner, builder of [AI Cloud Security Lab](https://www.skool.com/cloud-security-lab), occasional writer of skills like this one.

If this helped you, the kindest thing you can do is tell one other person in IT or security who's struggling to get started with AI tools.
