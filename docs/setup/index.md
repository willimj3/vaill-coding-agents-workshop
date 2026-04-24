# Setting Up Claude Code

**The terminal is the biggest hurdle.** Once you get past it, the rest follows. No coding experience required.

This section takes you from zero to a working Claude Code installation. If you want to see what coding agents *do* before setting one up, start with [What Are Coding Agents?](../agents/index.md).

!!! tip "Watch first: Claude Code for non-engineers (43 min)"
    Before diving into the install steps below, this video walkthrough by [Ally Miller](https://www.youtube.com/@allykmiller) is the best introduction we have found for non-technical users. She walks through the entire setup process, then demonstrates real tasks: creating and editing files, building a dashboard from a CSV, turning data into a presentation, managing files on your computer, and creating reusable agents — all in plain English with no coding background assumed.

    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; margin: 1rem 0;">
      <iframe src="https://www.youtube.com/embed/v1ynWeHhzXs" style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;" allowfullscreen loading="lazy"></iframe>
    </div>

    **Key moments:** Installation (~2:00) | Creating & editing files (~8:45) | CSV to dashboard (~13:45) | Dashboard to presentation (~22:45) | System utilities (~27:00) | Modes & settings (~33:00) | Creating agents (~36:20)

---

## How to Run Claude Code

**Our recommendation: just use the terminal.** The text-only command line that comes with your Mac or PC is all you need. It is the simplest path, it is what the install guides walk you through, and it is how we run Claude Code day to day. Black screen, blinking cursor -- that is the whole interface.

If you prefer a visual environment, you can optionally run Claude Code inside a **code editor** like [VS Code](https://code.visualstudio.com/) (free). A code editor gives you a file explorer, a text editor, and a built-in terminal all in one window. Claude Code runs in the editor's terminal, and you can watch its changes appear as color-coded highlights. This can be helpful for longer sessions where you want to see your files while you work.

| | **Terminal (recommended)** | **Code Editor (optional)** |
|---|---|---|
| **What it looks like** | Black screen, blinking cursor, text only | Visual file explorer on the left, editor in the center, Claude in a side panel |
| **Setup** | Just install Claude Code -- nothing else needed | Install VS Code + the Claude Code extension |
| **Best for** | Most tasks, quick iterations, keeping things simple | Longer sessions where you want to browse files visually |

If you do want a code editor, **[VS Code](https://code.visualstudio.com/)** is what we recommend -- it is free and has an official Claude Code extension. Either way, the code editor is optional -- everything on this site works from a plain terminal.

---

## Get Started (Do These in Order)

### Step 1: Install Claude Code

=== "Mac"

    **Open Terminal** (Cmd + Space -> "Terminal" -> Enter), then run:

    ```bash
    # Install Node.js first from https://nodejs.org (LTS version)
    node --version          # verify it worked

    # Then install Claude Code
    npm install -g @anthropic-ai/claude-code
    claude                  # first run — authenticates in browser
    ```

    Permission error? Use `sudo npm install -g @anthropic-ai/claude-code`

    [:octicons-arrow-right-24: Full Mac walkthrough](../toolkit/install-mac.md)

=== "Windows"

    **Open PowerShell** (Windows key -> "PowerShell" -> Enter), then run:

    ```powershell
    # Install Node.js first from https://nodejs.org (LTS version)
    node --version          # verify it worked

    # Then install Claude Code
    npm install -g @anthropic-ai/claude-code
    claude                  # first run — authenticates in browser
    ```

    Permission error? Right-click PowerShell -> "Run as administrator" and retry.

    [:octicons-arrow-right-24: Full Windows walkthrough](../toolkit/install-windows.md)

### Steps 2-4: Configure

| Step | What You'll Do | Time |
|------|---------------|------|
| **[Set Up VS Code](vscode-setup.md)** *(optional)* | Install VS Code and the Claude Code extension. Helpful for visual file browsing, but not required. | 15 min |
| **[Your CLAUDE.md](../toolkit/claude-md.md)** | Create the instruction file that makes Claude Code work *for you* -- your role, your courses, your research. | 30 min |
| **[MCP Setup](../toolkit/mcp-setup.md)** | Connect Claude Code to Gmail, Google Calendar, and other services. | 30-60 min |

<span id="how-claude-code-thinks"></span>
??? tip "How Claude Code Thinks"

    When you first launch Claude Code, you are in **Default mode** -- the safest starting point. Claude proposes changes and waits for you to approve each one before it touches your files. As you get comfortable, you can change that.

    **The Three Modes**

    | Mode | What Claude Does | What You See |
    |------|-----------------|-------------|
    | **Default** | Proposes edits as diffs. You confirm each one. | Normal prompt |
    | **Plan Mode** | Explores and proposes -- touches nothing. Reads files, suggests approaches. You decide. | `(plan)` label |
    | **Auto-Accept** | Applies edits automatically without asking. | `⏵⏵ accept edits on` |

    !!! warning "Accidentally in Auto-Accept?"
        If Claude started making changes without asking, look for the `⏵⏵` indicator. Press **Shift+Tab** until it disappears and you see the normal prompt. To undo changes: **Cmd+Z** (Mac) or **Ctrl+Z** (Windows) in VS Code.

    **How to Switch:** Press **Shift+Tab** to cycle through modes (Default -> Plan -> Auto-Accept -> Default). You can also type `/plan` to jump to Plan mode directly.

    **When to Use Each Mode**

    | Situation | Mode |
    |-----------|------|
    | "I want to understand what is in this project" | **Plan mode** -- Claude reads and proposes without touching files |
    | "Claude keeps asking me to approve small edits and I trust it" | **Auto-Accept** -- edits apply immediately |
    | "I want Claude to draft something but I want to review first" | **Default** -- Claude proposes, you confirm |
    | "I want Claude to explore options, then I'll decide" | **Plan mode**, then switch to Default to execute |

    **Start in Default mode.** Switch to Plan mode when you want Claude to think without acting, and to Auto-Accept when you are doing trusted, routine work and the confirmation prompts slow you down.

---

## Prerequisites

Before starting:

1. **Have used a chatbot** (Claude.ai or ChatGPT) at least a few times
2. **Have a paid Anthropic account** (Claude Pro at minimum; Claude Max recommended for heavy use)
3. **Be comfortable with the idea of using a terminal** -- you do not need experience, but you do need willingness

If you have not used chatbots much yet, start with [AI Essentials](../essentials/index.md) first.

---

## What You'll End Up With

After working through this section:

- **Claude Code installed and authenticated** on your computer
- **VS Code configured** with the Claude Code extension (optional)
- **A CLAUDE.md file** that tells Claude about your role, courses, research, and preferences
- **MCP integrations** connecting Claude to your email, calendar, and documents
- **A system that improves over time** as you refine your configuration and build workflows

The whole setup takes a few hours spread over a couple of sessions. The time investment pays for itself within the first week of regular use.

---

## Common Issues

If you get stuck during setup, check here before giving up:

| Problem | Fix |
|---------|-----|
| **`node: command not found`** | Close Terminal and reopen it. If that does not work, reinstall Node.js from [nodejs.org](https://nodejs.org). |
| **`npm: command not found`** | Same as above -- npm comes with Node.js. |
| **Permission errors during install** | Use `sudo npm install -g @anthropic-ai/claude-code` and enter your Mac password. |
| **Browser doesn't open for authentication** | Copy the URL from Terminal and paste it into your browser manually. |
| **Google OAuth tokens expire every 7 days** | Your Google Cloud project is in "Testing" mode. Switch to "Production" in the [Cloud Console](https://console.cloud.google.com) -> Google Auth platform -> Audience. See [MCP Setup](../toolkit/mcp-setup.md) for details. |
| **MCP server not responding** | Check that all paths in `~/.claude.json` are correct and absolute. Run `claude doctor` for diagnostics. Restart Claude Code. |
| **Claude can't see my files** | Make sure you opened a folder (`File -> Open Folder` in VS Code, or `cd` to the folder before running `claude`), not just a single file. |

For more help: [GitHub Issues](https://github.com/willimj3/vaill-coding-agents-workshop/issues).
