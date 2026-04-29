# Cowork: Agents Without the Terminal

Most of this guide focuses on Claude Code — a coding agent that lives in the terminal. But Anthropic offers a second, complementary tool that may be a better fit for many faculty: **Claude Cowork**. It runs in the Claude Desktop app, requires no terminal, and is built around a different premise — not conversation, not coding, but **task delegation**.

This page is our short orientation. The definitive guide to Cowork was written by **Chloe Keywell** ([@chlokey](https://chlokey.com)), and we encourage everyone interested in Cowork to read it directly.

!!! tip "Credit where due"
    This page draws on, and is meant as a faculty-oriented gateway to, [Chloe Keywell's "Claude Cowork" guide](https://chlokey.com/#what-is-cowork) — based, in her words, on "25+ iterations, 20+ research sessions, and months of real-world use." The framing of Chat vs. Code vs. Cowork, the nine-layer system, and several of the use cases below are hers. We have translated her examples into legal and academic settings; the original is broader and richer. **Read it at [chlokey.com](https://chlokey.com/#what-is-cowork).**

---

## What Is Cowork?

Keywell's clearest framing is a trichotomy. Three Anthropic products, three different relationships:

| Tool | What it is | Relationship |
|------|-----------|--------------|
| **Claude Chat** | "Prompt in, answer out. You stay in the conversation the entire time." | Conversation |
| **Claude Code** | "Lives inside your terminal, writes and executes real code, manages repositories." | Pair-programming partner |
| **Claude Cowork** | "You delegate a task, it breaks it into subtasks, spins up a virtual machine, and drops the finished output into your folder while you step away." | Task delegation |

Or, as she puts it more bluntly: **"Chat is a conversation. CoWork is task delegation. Completely different relationship. Completely different results."**

Cowork is not a chatbot you talk to. It is closer to an assistant you hand work to. You describe a task, walk away, and come back to a finished file — a draft, a research summary, a triaged inbox, a comparison table. The work happened in a sandboxed virtual machine; the output landed in a folder you specified.

---

## Why This Matters for Law Faculty

Most of our colleagues will never open a terminal. That is not a failure of will — it is a reasonable choice given the time costs. Cowork removes the terminal entirely. The interface is the Claude Desktop app, and the unit of interaction is the **task**, not the keystroke.

For faculty whose AI use is currently limited to the chat window, Cowork closes a gap that chat alone cannot:

- **Chat** can summarize a single document you paste in. **Cowork** can summarize the twelve PDFs sitting in a folder on your desktop and save the result back to that folder.
- **Chat** can draft an email. **Cowork** can draft an email *and* schedule a recurring morning briefing that pulls from your calendar and inbox.
- **Chat** is stateless across sessions unless you re-paste context. **Cowork** maintains persistent context, scheduled work, and connected tools.

If Claude Code is the right tool for faculty who want to dig in, Cowork is the right tool for faculty who want a competent assistant they can hand things to.

---

## The Nine-Layer System (from Keywell)

A central contribution of Keywell's guide is a nine-layer framework for setting Cowork up so it actually works as a delegated assistant rather than a glorified chatbot. The layers, in her ordering:

1. **Global Instructions** — How Claude should behave across every task
2. **CLAUDE.md** — Who you are (role, context, working style)
3. **Memory Files** — Deep context on specific topics or matters
4. **Folder Structure** — Where everything lives (she recommends the [PARA method](https://fortelabs.com/blog/para/))
5. **Custom Skills** — Pre-built, reusable workflows
6. **Scheduled Tasks** — Automations that run while you are away
7. **Session Continuity** — Handoff documentation so Claude picks up where it left off
8. **Connected Tools** — Gmail, Calendar, Notion, Drive
9. **Quick Capture** — Submit tasks from your phone

Several of these will be familiar from elsewhere in this guide. **CLAUDE.md** is covered in [Your CLAUDE.md](../toolkit/claude-md.md). **Folder structure** is covered in [AI Project Folders](../essentials/project-folders.md). **Custom Skills** are covered in [Skills & Agents Explained](../system/agents-vs-skills.md). The Cowork-specific layers are the scheduling, session continuity, connected tools, and quick capture — these are what turn a chatbot into a delegated assistant.

For setup detail, [Keywell's guide](https://chlokey.com/#initial-setup) is the canonical resource. Replicating her instructions here would not improve on the original.

---

## What This Looks Like for Faculty Work

Keywell gives a long list of examples — morning briefings, email drafting, interview prep, weekly reviews, inbox triage, trip planning, industry news, newsletter digests. The mechanics translate directly to legal and academic settings:

- **Morning briefing for a busy teaching week.** Cowork runs every weekday at 7am, scans your calendar and inbox, and drops a one-page brief into a folder: today's classes, students who emailed overnight, committee deadlines this week, anything urgent.
- **Inbox triage during conference travel.** Hand Cowork the rule "while I am away, draft replies to anything routine, flag anything from a current student, ignore listservs." Come back to a folder of drafts to review rather than 400 unread emails.
- **Weekly research digest.** A scheduled task that scans SSRN, the law-review submission trackers, and a handful of newsletters you trust, and produces a one-page summary every Friday afternoon.
- **Recurring grading assist.** Cowork pulls submitted exam responses from a folder, runs a first pass against the rubric you saved as a skill, and returns a draft annotation file for your review.

Each of these is a task you have probably done by hand, or wished you had time to do. None of them require touching a terminal.

!!! warning "Confidentiality boundary"
    Anything covered by [ABA Model Rule 1.6](https://www.americanbar.org/groups/professional_responsibility/publications/model_rules_of_professional_conduct/rule_1_6_confidentiality_of_information/) — client communications, identifiable client matters — does not belong in Cowork without an enterprise data agreement in place. The same caution we apply to chatbots applies here. Faculty work that does *not* implicate client confidences (course design, public scholarship, administrative correspondence) is the safer starting ground.

---

## Honest Considerations

- **Paid plan required.** Cowork is gated behind Claude Pro or Max. As of early 2026 there is no free tier.
- **Newer than Claude Code.** Documentation, third-party guides, and community knowledge are thinner. Keywell's guide is among the best resources currently available, which itself reflects how new the space is.
- **Desktop app, not browser.** Cowork runs inside the Claude Desktop application — fine on a personal laptop, potentially restricted on a managed institutional machine. Check with IT before assuming you can install it.
- **Output verification still required.** Delegating a task does not remove the obligation to read what comes back. Hallucinated citations and confident-but-wrong summaries do not become less of a risk because the work happened while you were at lunch.

---

## Read the Original

This page is a faculty-oriented summary, not a substitute for [Keywell's guide](https://chlokey.com/#what-is-cowork). Her treatment is more detailed, includes a setup checklist, and reflects significantly more hands-on experience than ours. If anything here piqued your interest, the next step is her site — not more pages on ours.

[:octicons-arrow-right-24: Read Chloe Keywell's full Cowork guide at chlokey.com](https://chlokey.com/#what-is-cowork){ .md-button .md-button--primary }
