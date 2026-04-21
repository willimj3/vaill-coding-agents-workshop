# Everyday Productivity

**AI workflows for the work every faculty member does — email, meetings, project tracking, and weekly planning. No legal expertise required.**

The legal-specific workflows elsewhere on this site are powerful, but the fastest way to see the value of AI tools is to point them at the work you already do every day. Every faculty member manages an inbox, sits in meetings, tracks projects, and tries to stay on top of a week that moves faster than they can. These workflows address that directly.

Some of these work in a browser chatbot. Others require Claude Code with MCP connections to your email and calendar. We note which is which.

!!! tip "Credit where due"
    Several of these workflows are adapted from [Chris Blattman's Claude Code system](https://claudeblattman.com/), an open-source project by a political economist at the University of Chicago who built and documented a full AI productivity workflow for managing research, communication, and teams. If you want deeper versions of these workflows — with custom skills, automated pipelines, and project dashboards — his site is the best resource available.

---

## Email Triage

**The problem:** You open your inbox on Monday morning and there are 87 unread messages. Some are urgent. Some are FYI. Some are committee threads where you were CC'd on reply-all chains that do not require your input. Sorting through them takes 30-45 minutes before you can start actual work.

**What you tell the agent:**

```text
Go through my unread email. Categorize each message as:
- ACTION REQUIRED — I need to respond or do something
- FYI — informational, no response needed
- LOW PRIORITY — newsletters, announcements, bulk messages

For anything in ACTION REQUIRED, draft a brief summary of what
is needed and suggest a response if appropriate. Flag anything
that mentions a deadline in the next 48 hours.
```

**What happens:** The agent scans your unread messages, categorizes them, and produces a prioritized summary. Action items are at the top with deadlines highlighted. FYI items are listed briefly. Low-priority items are noted but not summarized. You review the summary, handle the urgent items, and skip the rest — in 10 minutes instead of 45.

**What it replaces:** The cognitive overhead of scanning, sorting, and deciding what matters. You still make every decision about what to respond to and how — but the extraction and prioritization work is done for you.

**Requires:** Claude Code + [Gmail MCP](../toolkit/mcp-setup.md). This does not work in a browser chatbot because the agent needs to access your actual inbox.

---

## Meeting Follow-Up

**The problem:** You leave a faculty meeting, a committee call, or a student advising session with a head full of decisions, action items, and things you said you would do. You mean to write them down. You do not. By Thursday, half of it has evaporated.

**What you tell the agent:**

```text
Here are my notes from today's faculty committee meeting.
Extract:
1. Every decision that was made (who decided what)
2. Every action item (who is responsible, what is the deadline)
3. Any open questions that were raised but not resolved
4. Key discussion points worth remembering

Format the output as a structured summary I can paste into
an email to the committee.
```

**What happens:** The agent reads your notes — which can be rough, incomplete, stream-of-consciousness — and produces a clean, structured summary. Decisions are listed as decisions. Action items have names and deadlines attached. Open questions are flagged for follow-up.

**What it replaces:** The 20 minutes of post-meeting cleanup that you would otherwise skip. The structured output is also more useful than your raw notes when you need to reference the meeting weeks later.

**Requires:** This works in a browser chatbot — just paste your notes into Claude.ai or ChatGPT. If you use a meeting transcription tool (Otter, Granola, etc.), you can paste the transcript instead of notes for even better results. If you have Claude Code, you can point it at a transcript file directly.

---

## Weekly Review

**The problem:** Friday arrives and you cannot reconstruct what happened this week. You know you were busy. You know things moved forward. But if someone asked you for a status update on three projects, you would need to dig through email, calendar, and scattered notes to piece it together.

**What you tell the agent:**

```text
Review my email and calendar from this week (Monday through today).
Produce a weekly summary covering:

1. KEY ACCOMPLISHMENTS — what got done, what moved forward
2. OUTSTANDING ITEMS — things that were started but not finished,
   or commitments I made that I have not yet fulfilled
3. NEXT WEEK PREVIEW — what is on the calendar, what deadlines
   are approaching, what I should prepare for
4. FOLLOW-UPS NEEDED — people I owe responses to, threads that
   went quiet but need attention

Keep it concise. Bullet points, not paragraphs.
```

**What happens:** The agent scans your sent and received email, reviews your calendar events, and synthesizes a structured summary of your week. It catches things you forgot — a reply you never sent, a meeting you agreed to schedule but did not, a deadline mentioned in an email thread from Tuesday.

**What it replaces:** The Friday afternoon ritual of trying to remember what happened. More importantly, it catches the things that fell through the cracks — the action items you committed to in a Wednesday email that you have not thought about since.

**Requires:** Claude Code + [Gmail MCP](../toolkit/mcp-setup.md) + [Google Calendar MCP](../toolkit/mcp-setup.md). The agent needs access to both email and calendar to produce a useful synthesis.

---

## Project Tracking

**The problem:** You are juggling a law review article, a grant application, two committee responsibilities, and course prep for next semester. Each project has its own set of files, emails, and deadlines scattered across your computer and inbox. There is no single place where you can see the status of everything.

**What you tell the agent:**

```text
I am tracking these active projects:
1. Law review article on AI governance (target: August submission)
2. NSF grant proposal (deadline: October 15)
3. Curriculum committee — new course approval process
4. Fall semester course prep — AI and Legal Ethics seminar

For each project, search my email and files for any recent
activity. Produce a status dashboard with:
- Current status (on track / needs attention / stalled)
- Last activity (date and what it was)
- Next step (what needs to happen next)
- Upcoming deadlines

Save this as a markdown file at ~/projects/status-dashboard.md
```

**What happens:** The agent searches your email for threads related to each project, checks your files for recent edits, and builds a structured dashboard. It flags projects that have gone quiet (no email or file activity in two weeks) and highlights approaching deadlines. You review it, update anything the agent missed, and have a single document that tells you where everything stands.

**What it replaces:** The mental overhead of tracking multiple projects in your head. The dashboard becomes a living document — run the same prompt weekly and it updates automatically.

**Requires:** Claude Code + [Gmail MCP](../toolkit/mcp-setup.md). Works best with all MCP integrations connected, but even with just file access it can scan your project folders and produce useful status summaries.

---

## The Pattern

These four workflows share the same structure as every other workflow on this site:

1. **You describe the outcome** in plain English
2. **The agent handles the mechanical work** — scanning, sorting, extracting, formatting
3. **You provide the judgment** — deciding what matters, what to act on, what to delegate
4. **The output is a starting point** — review it, correct it, add what the agent missed

The difference between these and the legal-specific workflows is that these require zero domain expertise to set up. You can try email triage in the workshop open lab and have results in five minutes.

---

## Going Deeper

These are deliberately simple versions of workflows that can be much more sophisticated. For the full implementations — with custom skills, automated scheduling, project dashboards that write to Google Docs, and meeting-to-action-item pipelines — see [Chris Blattman's Claude Code system](https://claudeblattman.com/). His site documents the complete system he uses to manage research, teams, and communication across multiple countries, all built with Claude Code and no prior coding experience.

---

## Next Steps

<div class="grid cards" markdown>

-   **Connect your email and calendar**

    ---

    These workflows are most powerful with MCP integrations. The setup takes 30-60 minutes.

    [:octicons-arrow-right-24: MCP Setup](../toolkit/mcp-setup.md)

-   **Build your own workflows**

    ---

    Once you have the basics, start designing workflows for your specific practice or research.

    [:octicons-arrow-right-24: Build Your Own](../system/index.md)

-   **Try the prompt-plan-review loop**

    ---

    The same four-step method that powers these workflows. Works from day one.

    [:octicons-arrow-right-24: Your First Workflow](../workflows/first-session-skills.md)

</div>
