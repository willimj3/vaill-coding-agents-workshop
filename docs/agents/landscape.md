# The Agent Landscape

The coding agent space is moving fast. New tools launch monthly, existing tools add major features weekly, and the boundaries between categories keep shifting. This page provides a snapshot of the major players at time of publication — not to make you an expert on all of them, but to give you enough context to understand the options and make informed choices.

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

### OpenAI Codex

**What it is:** OpenAI's coding agent for writing, reviewing, and shipping code. It is available through several clients, including a local app, CLI, IDE extension, and Codex web.

**How it works:** Depending on the client, you can run Codex locally in your development environment or delegate cloud tasks through the web interface. You give instructions in plain English, connect the relevant workspace or repository, and review the agent's work.

**Strengths:** If you already use ChatGPT and are comfortable in the OpenAI ecosystem, Codex provides a familiar feel. It benefits from OpenAI's large model lineup.

**Considerations:** The product is evolving quickly, with plan-based usage limits and optional credit top-ups. For legal faculty, the key question is whether the Codex interface you choose fits your workflow better than Claude Code or Cowork.

---

### Claude Cowork (Anthropic)

**What it is:** A desktop task-delegation tool from Anthropic that brings Claude Code's agentic architecture into Claude Desktop for knowledge work beyond coding.

**How it works:** Instead of typing instructions into a terminal, you assign a task in Claude Desktop. Cowork can plan subtasks, work with local files, use connected tools, run code in an isolated space, and deliver outputs back to your file system. With computer use enabled, Claude may also interact with browser and desktop apps after you grant permissions.

**Strengths:** More approachable than terminal-based tools for users who find the command line intimidating. Useful for repetitive knowledge-work tasks that span local files, connected tools, and desktop applications.

**Considerations:** Newer than Claude Code, with a still-developing feature set. Requires a paid Claude plan and the Claude Desktop app. Some tasks remain better suited to Claude Code's terminal-based approach, especially data analysis and file processing at scale.

---

## Comparison Table

*This landscape changes rapidly — verify current pricing and features on each tool's website.*

| Tool | Interface | Best For | Starting Cost | Coding Experience Required? |
|------|-----------|----------|---------------|---------------------------|
| **Claude Code** | Terminal (text) | Complex reasoning tasks, legal analysis, file processing, workflow automation | Included with Claude subscription ($20/mo Pro) | No — designed for natural language use |
| **Claude Cowork** | Claude Desktop | Delegated knowledge-work tasks across files and apps | Included with paid Claude plans | No — visual task delegation |
| **OpenAI Codex** | App, CLI, IDE, web | Local and cloud coding tasks, code review | Included across ChatGPT plans; limits vary by plan | No — natural language interface |
| **Google Jules** | Web-based | Repository-aware coding tasks | Introductory access; higher limits with Google AI Pro/Ultra | No — natural language interface |

---

## What We Mean by "Coding Experience Required"

This deserves clarification. None of these tools require us to *write* code in the traditional sense. We give instructions in English; the tool figures out the technical details. However:

- **Terminal-based tools** (Claude Code) require comfort with a text-based interface — no icons, no menus, just typing. That is a learnable skill, and we cover it in the [Setup section](../setup/index.md), but it is a real adjustment.
- **Visual tools** (Claude Cowork, Codex web, Jules) present a more familiar interface but are newer and still developing their feature sets.
- **The practical reality:** For the tasks we care about in legal work — analyzing documents, drafting memos, managing data — Claude Code's conversational interface turns out to be the most natural fit, despite the terminal. We describe what we want; it does the work.

---

## A Rapidly Evolving Space

By the time you read this, some details on this page may already be outdated. A tool may have added new features, changed pricing, or been acquired. New competitors may have launched.

That is fine. The underlying concepts — giving clear instructions, providing context, verifying output, maintaining human judgment — do not change with the tool. We are learning a **way of working**, not just a specific product.

!!! note "Keeping current"
    The [Resources](../resources.md) page includes links to newsletters and communities that track the coding agent landscape. If you find this space interesting, those are good ways to stay informed without being overwhelmed.
