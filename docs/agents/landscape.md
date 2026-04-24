# The Agent Landscape

The coding agent space is moving fast. New tools launch monthly, existing tools add major features weekly, and the boundaries between categories keep shifting. This page provides a snapshot of the major players as of early 2026 — not to make you an expert on all of them, but to give you enough context to understand the options and make informed choices.

!!! tip "Skills transfer across tools"
    We use Claude Code in this guide, but the concepts transfer directly to every tool on this page. Learning to describe tasks clearly, provide good context, and verify AI output are universal skills. If you switch tools later, you will not be starting over.

---

## The Major Tools

### Claude Code (Anthropic)

**What it is:** A terminal-based coding agent that runs on your computer. You type natural language instructions; it reads your files, runs commands, and builds things.

**How it works:** You open a terminal window (the text-based interface on your computer), start Claude Code, and have a conversation. Unlike a chatbot, Claude Code can see your file system, create and edit documents, run programs, and connect to external services like email and calendar through a protocol called MCP.

**Strengths:** Excellent documentation, strong reasoning for complex tasks, persistent project memory through CLAUDE.md files, and the MCP protocol for connecting to other tools. Active development community with frequent updates.

**Considerations:** The terminal interface can feel unfamiliar at first. Heavy use requires a paid subscription.

---

### OpenAI Codex (ChatGPT CLI)

**What it is:** OpenAI's answer to Claude Code — a command-line agent that can read files and execute tasks on your computer, powered by the same models behind ChatGPT.

**How it works:** Similar concept to Claude Code. You interact through a terminal, give instructions in plain English, and the agent takes action on your files and system.

**Strengths:** If you already use ChatGPT and are comfortable in the OpenAI ecosystem, Codex provides a familiar feel. It benefits from OpenAI's large model lineup.

**Considerations:** Newer to market than Claude Code, with a still-developing documentation base. The tool landscape may look different by the time you read this.

---

### Claude Co-work (Anthropic)

**What it is:** A desktop automation tool from Anthropic that lets Claude operate autonomously on your computer — browsing the web, working with local files, using desktop applications, and completing multi-step tasks with a visual interface rather than a terminal.

**How it works:** Instead of typing instructions into a terminal, you interact through a visual sandbox where you can watch Claude work. It can open applications, navigate websites, fill out forms, and manage files — similar to what a human assistant would do sitting at your computer.

**Strengths:** More approachable than terminal-based tools for users who find the command line intimidating. Can interact with desktop applications and websites that terminal-based agents cannot. Built-in security boundaries.

**Considerations:** Newer than Claude Code, with a still-developing feature set. Requires a Claude subscription. Some tasks are better suited to Claude Code's terminal-based approach (especially data analysis and file processing at scale).

---

## Comparison Table

*Prices and features as of early 2026. This landscape changes rapidly — verify current details on each tool's website.*

| Tool | Interface | Best For | Starting Cost | Coding Experience Required? |
|------|-----------|----------|---------------|---------------------------|
| **Claude Code** | Terminal (text) | Complex reasoning tasks, legal analysis, file processing, workflow automation | Included with Claude subscription ($20/mo Pro) | No — designed for natural language use |
| **Claude Co-work** | Visual desktop | Desktop automation, web browsing, working with applications | Included with Claude subscription | No — visual, point-and-click interaction |
| **OpenAI Codex** | Web-based | Asynchronous task execution, code generation | Included with ChatGPT plans ($20/mo Plus) | No — natural language interface |
| **Google Jules** | Web-based | Repository-aware coding tasks | Included with Gemini AI Pro ($20/mo) | No — natural language interface |

---

## What We Mean by "Coding Experience Required"

This deserves clarification. None of these tools require us to *write* code in the traditional sense. We give instructions in English; the tool figures out the technical details. However:

- **Terminal-based tools** (Claude Code) require comfort with a text-based interface — no icons, no menus, just typing. That is a learnable skill, and we cover it in the [Setup section](../setup/index.md), but it is a real adjustment.
- **Visual tools** (Claude Co-work, Codex, Jules) present a more familiar interface but are newer and still developing their feature sets.
- **The practical reality:** For the tasks we care about in legal work — analyzing documents, drafting memos, managing data — Claude Code's conversational interface turns out to be the most natural fit, despite the terminal. We describe what we want; it does the work.

---

## A Rapidly Evolving Space

By the time you read this, some details on this page may already be outdated. A tool may have added new features, changed pricing, or been acquired. New competitors may have launched.

That is fine. The underlying concepts — giving clear instructions, providing context, verifying output, maintaining human judgment — do not change with the tool. We are learning a **way of working**, not just a specific product.

!!! note "Keeping current"
    The [Resources](../resources.md) page includes links to newsletters and communities that track the coding agent landscape. If you find this space interesting, those are good ways to stay informed without being overwhelmed.
