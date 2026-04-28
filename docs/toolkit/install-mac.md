# Install Claude Code (Mac)

**A beginner's guide for Terminal newcomers. No prior command-line experience needed.**

---

## What Is Claude Code?

You have probably used Claude through a web browser at claude.ai -- type a question, get an answer. Claude Code is the same Claude, but running in **Terminal** instead of your browser.

**Why does that matter?**

| Claude.ai (browser) | Claude Code (Terminal) |
|---------------------|------------------------|
| You copy/paste files into the chat | Claude reads files directly from your computer |
| You copy/paste code back out | Claude edits files directly |
| Limited to what you type or upload | Can search your folders, run scripts, send emails |
| Isolated from your workflow | Integrated into your workflow |

Think of it this way: Claude.ai is like texting a smart friend. Claude Code is like having that friend sit at your computer with you.

!!! tip "Prefer a graphical interface?"
    If the terminal feels intimidating, Anthropic now offers a [Desktop app](https://claude.ai/api/desktop/darwin/universal/dmg/latest/redirect?utm_source=claude_code&utm_medium=docs) that lets you use Claude Code without the terminal. Download, install, and run -- no command line needed. See the [Desktop quickstart](https://code.claude.com/docs/en/desktop-quickstart) for details.

---

## Prerequisites

- **A Mac** running macOS 13.0 or later (Windows? See [Install -- Windows](install-windows.md))
- **Internet connection**
- **A paid Anthropic account** -- Claude Code requires a **Pro, Max, Team, or Enterprise** subscription. The free Claude.ai plan does not include Claude Code access. Sign up at [claude.ai](https://claude.ai) if you do not have one.

---

## Step 1: Open Terminal

### What is Terminal?

Terminal is a text-based interface to your computer. Instead of clicking on folders and files, you type commands. It looks old-fashioned, but it is powerful -- and it is how Claude Code runs.

You do not need to become a Terminal expert. You just need to know how to open it and type a few commands.

### How to open Terminal

1. Press **Cmd + Space** to open Spotlight search
2. Type **Terminal**
3. Press **Enter**

A window will appear with a blank screen and a prompt that looks something like:

```
yourusername@your-mac ~ %
```

The `%` (or sometimes `$`) is where you type commands.

**Do not panic at the blank screen.** Terminal is just waiting for you to tell it what to do.

---

## Step 2: Install Claude Code

One command. No other software to install first.

Copy and paste this into Terminal and press Enter:

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**What to expect:** You will see text scrolling by as it downloads and installs. Wait until you see your prompt (`%` or `$`) appear again with a message that says installation is complete.

This typically takes under a minute.

!!! tip "Alternative install methods"
    **Homebrew:** If you use Homebrew, you can install with `brew install --cask claude-code` instead.

    **npm:** If you already have Node.js 18+, you can install with `npm install -g @anthropic-ai/claude-code`. Note: do **not** use `sudo` with npm installs -- it can cause permission issues.

    For all install options, see the [official setup guide](https://code.claude.com/docs/en/getting-started).

---

## Step 3: First Run and Authentication

The first time you run Claude Code, you need to link it to your Anthropic account. This is a one-time setup.

In Terminal, type:

```bash
claude
```

And press Enter.

**What happens next:**

1. Your web browser will open automatically
2. You will see an Anthropic login page
3. Log in with your Anthropic account (Pro, Max, Team, or Enterprise)
4. Click "Approve" or "Authorize" when asked to give Terminal access
5. Return to Terminal -- you should see a welcome message

**You are in.** Claude Code is now running.

---

## Step 4: Your First Conversation

Once Claude Code is running, you will see a prompt where you can type messages. Just type like you would in any chat:

```
> What files are in my current folder?
```

Press Enter, and Claude will respond -- but now Claude can actually look at your files and tell you what is there.

!!! ask-claude "Not sure what to do first?"
    In the Claude Code terminal, try typing:
    `I just installed Claude Code. I'm a law professor who teaches Contracts and writes about regulatory compliance. What's the most useful thing I can do in the next 10 minutes?`
    Press Enter. Claude will walk you through getting started based on your role.

### Useful to Know

| Action | How |
|--------|-----|
| Send a message | Type and press **Enter** |
| Multi-line message | Press **\\** then **Enter** for a new line without sending |
| Queue a message while Claude works | Just type -- it will be sent when Claude is ready |
| Scroll through past messages | **Up/Down** arrow keys |
| Get help | Type `/help` |
| Exit | Type `/exit` or press **Ctrl + C** |

---

## Step 5: Opening Claude Code Again

After the first-time setup, you do not need to repeat the install or authentication. From now on:

### Starting a new session

1. Open Terminal (Cmd + Space -> "Terminal" -> Enter)
2. Type `claude` and press Enter

That is it.

### Where you start matters

Claude Code pays attention to **which folder you are in** when you start it. If you are working on a specific project, navigate to that folder first:

```bash
cd ~/Desktop/article-draft
claude
```

This way Claude can see and work with the files in that project.

### Resuming a previous session

| Command | What It Does |
|---------|--------------|
| `claude -c` | **Continue** -- picks up your most recent conversation in the current folder |
| `claude --resume` | **Resume** -- shows a list of recent conversations so you can choose which one |

**`claude -c`** is the one you will use most. You were working on something, you closed Claude Code, and now you want to keep going.

---

## Updates

The native installer keeps Claude Code up to date automatically. Updates download in the background and take effect the next time you start Claude Code. You do not need to do anything.

To update manually at any time:

```bash
claude update
```

To check your current version:

```bash
claude --version
```

---

!!! tip "What Claude Code can access"
    Claude Code can read any file in the folder where you run it -- and, if asked, files elsewhere on your machine, including cloud-synced folders (Dropbox, iCloud, Google Drive). It can also run terminal commands. This is what makes it powerful: Claude works *with* your files, not in a separate sandbox. When Claude reads a file or processes data, that content is sent to Anthropic's API. Anthropic's [data policy](https://www.anthropic.com/policies/privacy) states API inputs are not used for model training. For more on data handling, see [Privacy](../privacy.md).

## What's Next

You have installed Claude Code and had your first conversation. The recommended next steps:

1. **[Set up your CLAUDE.md file](claude-md.md)** -- This tells Claude about you, your courses, your research, and your preferences so every session starts with context. (~30 minutes)

2. **[How Claude Code Thinks](../setup/index.md#how-claude-code-thinks)** -- Understand the three modes that control Claude's behavior (Default, Plan, Auto-Accept). (~5 minute read)

3. **[Connect external services](mcp-setup.md)** -- Give Claude access to Gmail, Google Docs, or Calendar so it can help with real tasks. (~30-60 minutes)

---

## Quick Reference

| Task | Command |
|------|---------|
| Open Terminal | Cmd + Space -> "Terminal" -> Enter |
| Install Claude Code | `curl -fsSL https://claude.ai/install.sh \| bash` |
| Start Claude Code | `claude` |
| Continue last session | `claude -c` |
| Resume a past session | `claude --resume` |
| Update Claude Code | `claude update` |
| Check version | `claude --version` |
| Get help | `/help` |
| Exit | `/exit` or Ctrl+C |

---

## Troubleshooting

**Installation fails** -- Make sure you are running macOS 13.0 or later. Check your internet connection.

**Browser doesn't open for authentication** -- Copy the URL from Terminal and paste it into your browser manually.

**"Free plan" error on authentication** -- Claude Code requires a paid plan (Pro, Max, Team, or Enterprise). The free Claude.ai plan does not include Claude Code access. Upgrade at [claude.ai](https://claude.ai).

**Claude Code feels slow** -- The first response in a session can take a few seconds as it loads context. Subsequent responses are faster.

**Other issues** -- Run `claude doctor` for diagnostics, or see the [official troubleshooting guide](https://code.claude.com/docs/en/troubleshooting).
