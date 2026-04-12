# Why Claude Code?

With several capable coding agents available, a fair question is: why does this workshop use Claude Code specifically? This page explains our reasoning — and, just as importantly, the honest downsides.

---

## The Case for Claude Code

### Best-in-Class Documentation and Onboarding

Claude Code has the most comprehensive documentation of any coding agent available today. Anthropic has invested heavily in guides, tutorials, and explanations aimed at people who have never used a terminal before. For a workshop serving law faculty with little or no coding background, this matters enormously. When we leave the room, participants need to be able to continue learning on their own, and good documentation is what makes that possible.

### Strong Reasoning for Complex Tasks

Legal work demands careful reasoning — synthesizing multiple documents, tracking exceptions and conditions, identifying inconsistencies, maintaining logical structure across long arguments. Claude's underlying models (particularly Opus) are consistently strong at these tasks. When we ask Claude Code to analyze a contract or draft a research memo, the quality of its reasoning is noticeably better than many alternatives for this type of work.

### CLAUDE.md: Persistent Project Memory

Claude Code uses a simple but powerful system for maintaining context across sessions: a file called `CLAUDE.md` that lives in your project folder. In this file, we describe the project, our preferences, common tasks, and anything the agent should always know. Every time we start a new conversation, Claude Code reads this file first.

For legal work, this is valuable. We can tell it: "This is a family law practice. Our clients are primarily middle-income individuals in Davidson County. We file in Tennessee state courts. Our writing style is direct and avoids legalese where possible." Every interaction from that point forward is shaped by that context.

### MCP: Connecting to Email, Calendar, and More

The Model Context Protocol (MCP) is an open standard that lets Claude Code connect to external services — email, calendar, databases, cloud storage, and more. This means Claude Code is not limited to files on our computer. It can search our email for relevant messages, check our calendar for scheduling conflicts, or pull data from a shared drive.

For law faculty juggling teaching, research, committee work, and possibly a practice, these connections turn a file-reading tool into something closer to a digital assistant.

### Accessible Pricing

Claude Code offers a free tier that is sufficient for experimentation and light use. The Pro tier ($20/month as of early 2026) provides enough capacity for regular daily use. The Max tier ($100-200/month) is available for heavy users, but most faculty will find Pro more than adequate.

Critically, there is no separate charge for Claude Code itself — it is included with a Claude subscription. We are not asking participants to buy an additional product.

### Active Development and Community

Anthropic updates Claude Code frequently, often weekly. The user community is large and active, which means questions get answered, problems get solved, and best practices circulate quickly. For a tool we are recommending to colleagues, ongoing support and momentum matter.

---

## The Honest Downsides

We would not be doing our jobs as legal educators if we only presented the positive case. Here are the real limitations:

### The Terminal Can Be Intimidating

Claude Code runs in a terminal — a text-based interface with no buttons, no menus, and no graphical elements. For anyone who has never opened a terminal before, the first few minutes can feel disorienting. We address this directly in the [Setup section](../setup/index.md) with step-by-step instructions, but it would be dishonest to pretend the learning curve does not exist.

The good news: most participants report that the terminal feels comfortable within 30-60 minutes of use. The interface is simple precisely because there is so little to learn — we type what we want, and the agent responds.

### Subscription Required for Serious Use

The free tier has meaningful limits. Anyone who plans to use Claude Code regularly for substantive work will need a paid subscription. At $20/month, this is comparable to other professional tools, but it is a recurring cost that some may find hard to justify without institutional support.

### Anthropic Is a Single Vendor

By choosing Claude Code, we are building workflows around one company's product. If Anthropic changes pricing, discontinues features, or goes in a direction that no longer serves our needs, migration takes effort. This is a real consideration.

The mitigation: the skills we learn — describing tasks clearly, structuring prompts, verifying output — transfer to any tool. We are not learning Claude Code syntax. We are learning how to work with AI agents, and Claude Code happens to be the best vehicle for that learning today.

### Not Everything Works on the First Try

Claude Code is powerful, but it is not magic. Complex tasks sometimes require multiple attempts, clarification, or a different approach. The agent may misunderstand an instruction, take an unexpected path, or produce output that needs significant revision. This is normal and expected — but it can be frustrating for someone expecting a polished experience from the start.

### Cloud-Based Processing

When we use Claude Code, our instructions and file contents are sent to Anthropic's servers for processing. This has implications for confidentiality and data privacy that we address in detail in [Limitations & Risks](limitations.md). For now, the key point: this is not a tool for processing privileged client communications without careful thought about what we are sending and to whom.

---

## The Bottom Line

We chose Claude Code because it offers the best combination of accessibility, reasoning quality, and extensibility for legal professionals who are new to coding agents. It is not the only good option, and it is not without drawbacks. But for the specific task of this workshop — helping law faculty understand and begin using coding agents — it is the right tool for the job.

!!! tip "Your mileage may vary"
    If you explore other tools after this workshop and find that Cursor, Copilot, or something else fits your workflow better, that is a perfectly good outcome. The goal is not Claude Code loyalty. The goal is AI fluency — and that is portable.
