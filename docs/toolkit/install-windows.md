# Install Claude Code (Windows)

**A beginner's guide for PowerShell newcomers. No prior command-line experience needed.**

---

## What Is Claude Code?

You have probably used Claude through a web browser at claude.ai -- type a question, get an answer. Claude Code is the same Claude, but running in **PowerShell** instead of your browser.

**Why does that matter?**

| Claude.ai (browser) | Claude Code (PowerShell) |
|---------------------|--------------------------|
| You copy/paste files into the chat | Claude reads files directly from your computer |
| You copy/paste code back out | Claude edits files directly |
| Limited to what you type or upload | Can search your folders, run scripts, send emails |
| Isolated from your workflow | Integrated into your workflow |

Think of it this way: Claude.ai is like texting a smart friend. Claude Code is like having that friend sit at your computer with you.

!!! tip "Prefer a graphical interface?"
    If the terminal feels intimidating, Anthropic now offers a [Desktop app](https://claude.com/download?utm_source=claude_code&utm_medium=docs) that lets you use Claude Code without the terminal. Download, install, and run -- no command line needed. See the [Desktop quickstart](https://code.claude.com/docs/en/desktop-quickstart) for details.

---

## Prerequisites

- **A Windows PC** running Windows 10 (version 1809 or later) or Windows 11
- **Internet connection**
- **Git for Windows** -- required for Claude Code to run commands. Download from [git-scm.com/downloads/win](https://git-scm.com/downloads/win) and install with default settings.
- **A paid Anthropic account** -- Claude Code requires a **Pro, Max, Team, or Enterprise** subscription. The free Claude.ai plan does not include Claude Code access. Sign up at [claude.ai](https://claude.ai) if you do not have one.

---

## Step 1: Install Git for Windows

If you do not already have Git installed, do this first:

1. Go to [git-scm.com/downloads/win](https://git-scm.com/downloads/win)
2. Download the installer
3. Run it and accept the default settings (click Next through each screen)
4. When it finishes, **close and reopen PowerShell** if you had it open

Claude Code uses Git for Windows internally to execute commands. You do not need to learn Git -- just install it.

---

## Step 2: Open PowerShell

### What is PowerShell?

PowerShell is a text-based interface to your computer. Instead of clicking on folders and files, you type commands. It looks old-fashioned, but it is powerful -- and it is how Claude Code runs.

You do not need to become a PowerShell expert. You just need to know how to open it and type a few commands.

### How to open PowerShell

1. Press the **Windows key** on your keyboard
2. Type **PowerShell**
3. Click **Windows PowerShell** from the results

A window will appear with a blue or black background and a prompt that looks something like:

```
PS C:\Users\YourName>
```

The `>` is where you type commands. The `PS` at the beginning tells you that you are in PowerShell (not CMD -- this matters for the install command).

**Do not panic at the blank screen.** PowerShell is just waiting for you to tell it what to do.

---

## Step 3: Install Claude Code

One command. No other software to install first (other than Git, which you did in Step 1).

Copy and paste this into PowerShell and press Enter:

```powershell
irm https://claude.ai/install.ps1 | iex
```

**What to expect:** You will see text scrolling by as it downloads and installs. Wait until you see your prompt (`>`) appear again with a message that says installation is complete.

!!! warning "Getting an error about tokens?"
    If you see `The token '&&' is not a valid statement separator`, you are in PowerShell but used the wrong command. The command above (`irm ... | iex`) is the correct one for PowerShell.

    If you see `'irm' is not recognized`, you are in CMD, not PowerShell. Either switch to PowerShell, or use this CMD command instead:
    ```
    curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd
    ```

!!! tip "Alternative install methods"
    **WinGet:** If you use WinGet, you can install with `winget install Anthropic.ClaudeCode` instead.

    **npm:** If you already have Node.js 18+, you can install with `npm install -g @anthropic-ai/claude-code`. Note: do **not** use elevated permissions -- it can cause issues.

    For all install options, see the [official setup guide](https://code.claude.com/docs/en/getting-started).

---

## Step 4: First Run and Authentication

The first time you run Claude Code, you need to link it to your Anthropic account. This is a one-time setup.

In PowerShell, type:

```powershell
claude
```

And press Enter.

**What happens next:**

1. Your web browser will open automatically
2. You will see an Anthropic login page
3. Log in with your Anthropic account (Pro, Max, Team, or Enterprise)
4. Click "Approve" or "Authorize" when asked to give access
5. Return to PowerShell -- you should see a welcome message

**You are in.** Claude Code is now running.

---

## Step 5: Your First Conversation

Once Claude Code is running, just type like you would in any chat:

```
> What files are in my current folder?
```

Press Enter, and Claude will respond -- but now Claude can actually look at your files and tell you what is there.

!!! ask-claude "Not sure what to do first?"
    In the Claude Code terminal, try typing:
    `I just installed Claude Code. I'm a law professor who teaches Constitutional Law and writes about judicial decision-making. What's the most useful thing I can do in the next 10 minutes?`
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

## Step 6: Opening Claude Code Again

After the first-time setup, you do not need to repeat the install or authentication. From now on:

### Starting a new session

1. Open PowerShell (Windows key -> "PowerShell" -> Enter)
2. Type `claude` and press Enter

That is it.

### Where you start matters

Claude Code pays attention to **which folder you are in** when you start it. If you are working on a specific project, navigate to that folder first:

```powershell
cd ~\Desktop\article-draft
claude
```

### Resuming a previous session

| Command | What It Does |
|---------|--------------|
| `claude -c` | **Continue** -- picks up your most recent conversation in the current folder |
| `claude --resume` | **Resume** -- shows a list of recent conversations so you can choose which one |

**`claude -c`** is the one you will use most. You were working on something, closed Claude Code, and now want to keep going.

---

## Updates

The native installer keeps Claude Code up to date automatically. Updates download in the background and take effect the next time you start Claude Code. You do not need to do anything.

To update manually at any time:

```powershell
claude update
```

To check your current version:

```powershell
claude --version
```

---

!!! tip "What Claude Code can access"
    Claude Code can read any file in the folder where you run it -- and, if asked, files elsewhere on your machine, including cloud-synced folders (OneDrive, Dropbox, Google Drive). It can also run commands. This is what makes it powerful: Claude works *with* your files, not in a separate sandbox. When Claude reads a file or processes data, that content is sent to Anthropic's API. Anthropic's [data policy](https://www.anthropic.com/policies/privacy) states API inputs are not used for model training. For more on data handling, see [Privacy](../privacy.md).

## What's Next

1. **[Set up your CLAUDE.md file](claude-md.md)** -- Tells Claude about you, your courses, your research, and your preferences. (~30 minutes)
2. **[How Claude Code Thinks](../setup/index.md#how-claude-code-thinks)** -- Understand the three modes that control Claude's behavior (Default, Plan, Auto-Accept). (~5 minute read)
3. **[Connect external services](mcp-setup.md)** -- Give Claude access to Gmail, Google Docs, etc. (~30-60 minutes)

---

## Troubleshooting

**`'irm' is not recognized`** -- You are in CMD, not PowerShell. Open PowerShell instead (Windows key -> "PowerShell").

**`The token '&&' is not a valid statement separator`** -- You are in PowerShell but used the CMD install command. Use `irm https://claude.ai/install.ps1 | iex` instead.

**Git-related errors** -- Make sure Git for Windows is installed from [git-scm.com/downloads/win](https://git-scm.com/downloads/win). Close and reopen PowerShell after installing Git.

**"Free plan" error on authentication** -- Claude Code requires a paid plan (Pro, Max, Team, or Enterprise). The free Claude.ai plan does not include Claude Code access. Upgrade at [claude.ai](https://claude.ai).

**Execution policy errors** -- Run this command first, then try the install again:
```powershell
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned
```
Type **Y** and press Enter when prompted.

**Browser doesn't open for authentication** -- Copy the URL from PowerShell and paste it into your browser manually.

**Other issues** -- Run `claude doctor` for diagnostics, or see the [official troubleshooting guide](https://code.claude.com/docs/en/troubleshooting).

---

## Quick Reference

| Task | Command |
|------|---------|
| Open PowerShell | Windows key -> "PowerShell" -> Enter |
| Install Claude Code | `irm https://claude.ai/install.ps1 \| iex` |
| Start Claude Code | `claude` |
| Continue last session | `claude -c` |
| Resume a past session | `claude --resume` |
| Update Claude Code | `claude update` |
| Check version | `claude --version` |
| Get help | `/help` |
| Exit | `/exit` or Ctrl+C |
