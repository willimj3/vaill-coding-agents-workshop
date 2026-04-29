# Your CLAUDE.md File

A `CLAUDE.md` file is a personal instruction document that Claude Code reads automatically every time you start a session. It tells Claude who you are, how you work, what tools you use, and what you need help with.

Without it, every session starts fresh. With it, Claude begins each session already understanding your context.

!!! note "Same file, second use"
    The CLAUDE.md convention also anchors [Claude Cowork](../agents/cowork.md) — the desktop, non-terminal counterpart to Claude Code. If you set this file up well once, both tools benefit from it.

---

## Why This Matters

A good CLAUDE.md file:

- **Saves time** -- No more repeating "I'm a law professor working on X using Y tools"
- **Improves responses** -- Claude tailors suggestions to your actual workflow and skill level
- **Reduces errors** -- When Claude knows where your files live, it gives relevant paths and suggestions
- **Compounds** -- As you refine the document, Claude gets better at helping you

The investment is small (20-30 minutes to start) and the payoff grows with every session.

---

## Where to Store It

### Single Computer

Claude Code looks for your CLAUDE.md here:

```
~/.claude/CLAUDE.md
```

The `~` means your home folder. The `.claude` folder is hidden (folders starting with `.` are hidden by default).

**To create it on Mac** (`mkdir -p` creates a folder; `~` means your home directory):
```bash
mkdir -p ~/.claude
```

**To see hidden files in Finder:** Press `Cmd + Shift + .`

### Multiple Computers (Recommended)

If you work across machines, store your CLAUDE.md in a synced folder and create a symlink:

A symlink is a shortcut -- it makes a file appear in two places at once. `ln -sf` creates one. This lets you store the real file in a synced folder while Claude Code finds it in its expected location.

```bash
# Store the real file in your cloud sync folder
# (replace with your actual path — Dropbox, OneDrive, iCloud, etc.)
mkdir -p ~/Dropbox/Claude/Settings

# Create the symlink so Claude Code finds it
mkdir -p ~/.claude
ln -sf ~/Dropbox/Claude/Settings/CLAUDE.md ~/.claude/CLAUDE.md
```

Repeat the symlink step on each computer. Now your CLAUDE.md syncs automatically.

!!! ask-claude "Not sure the symlink worked?"
    In the Claude Code terminal, type:
    `I set up the symlink but I'm not sure it worked. Can you verify it's connected properly?`
    Press Enter. Claude can check the symlink and tell you if it is pointing to the right file.

---

## Law Professor Template

Copy this template and fill in the sections relevant to you. Delete any sections that do not apply.

````markdown
# Claude Context: [Your Name]

## Who I Am

[1-2 sentences about your role. Example: "Associate Professor of Law at
[University], specializing in [area]. I teach [courses] and direct the
[clinic/center]."]

## My Primary Work

- Teaching: [list courses, e.g., Contracts, Constitutional Law, Seminar in Law & Technology]
- Scholarship: [current research areas, e.g., regulatory compliance, judicial decision-making]
- Service: [committees, clinics, centers, e.g., Faculty Appointments Committee, Innocence Project clinic]

## Tools and Software

| Tool | What I Use It For | Where Files Live |
|------|-------------------|------------------|
| Westlaw/LexisNexis | Case research, statutory lookups | Browser-based |
| SSRN | Publishing and tracking working papers | ssrn.com |
| Google Docs | Drafting, collaboration with co-authors | Google Drive |
| Canvas/Brightspace | Course management, student submissions | University LMS |
| Zotero | Citation management, bibliography | Local + zotero.org |

## Where My Files Are Stored

- **Course materials:** [e.g., ~/Google Drive/Courses/]
- **Article drafts:** [e.g., ~/Dropbox/Scholarship/]
- **Committee work:** [e.g., ~/Documents/Faculty Committees/]
- **Student materials:** [University LMS — Claude cannot access]

## What I Need Help With

- Drafting and revising article sections
- Preparing course materials and exam questions
- Summarizing and organizing case law research
- Writing committee memos and reports
- Managing email correspondence
- Formatting citations and bibliographies

## My Skill Level

- **Coding:** [e.g., "None — explain everything in plain language"]
- **Legal research databases:** [e.g., "Expert with Westlaw, basic LexisNexis"]
- **Command line:** [e.g., "Beginner — explain commands before running them"]
- **Document tools:** [e.g., "Comfortable with Word and Google Docs"]

## How I Prefer to Work

- [e.g., "Explain what you're doing before making changes"]
- [e.g., "Ask before modifying files outside my project"]
- [e.g., "Use formal but accessible language — I write for law reviews, not newspapers"]
- [e.g., "I use dictation, so prompts may be conversational"]

## Current Projects

| Project | My Role | Current Phase |
|---------|---------|---------------|
| [e.g., Law review article on AI regulation] | [Lead author] | [Drafting Section III] |
| [e.g., Fall Contracts syllabus] | [Instructor] | [Selecting new cases] |
| [e.g., Faculty hiring committee report] | [Committee chair] | [Compiling candidate evaluations] |
````

!!! ask-claude "Let Claude help you fill it in."
    In the Claude Code terminal, type something like:
    `Help me fill out my CLAUDE.md. I'm a law professor who teaches Torts and Evidence and writes about mass tort litigation.`
    Press Enter. Claude will ask follow-up questions and draft sections for you.

---

## Good vs. Underdeveloped

### Underdeveloped (Too Vague)

```markdown
# About Me
I'm a law professor. I teach and do research.
I use Westlaw and Word.
```

This does not give Claude enough to work with. What courses? What research area? Where are your files stored? What is your skill level?

### Good (Specific and Actionable)

```markdown
# Claude Context: Professor Sarah Chen

## Who I Am
Associate Professor of Law at Vanderbilt, specializing in
administrative law and regulatory compliance. I teach Administrative
Law (fall) and Legislation & Regulation (spring), and I direct the
Regulatory Policy Clinic.

## My Primary Work
- Teaching: Administrative Law, Legislation & Regulation, Regulatory Policy Clinic
- Scholarship: Article on agency deference post-Loper Bright, co-authored empirical
  study of notice-and-comment rulemaking, book chapter on regulatory sandboxes
- Service: Faculty Appointments Committee (chair), Law School Curriculum Committee

## Tools and Software

| Tool | What I Use It For | Where Files Live |
|------|-------------------|------------------|
| Westlaw | Case research, reg history | Browser |
| SSRN | Working paper distribution | ssrn.com |
| Google Docs | Drafts, co-author collaboration | Google Drive |
| Canvas | Course management | University LMS |
| Zotero | Citations, bibliography | Local + cloud sync |

## Where My Files Are Stored
- Course materials: ~/Google Drive/Teaching/
- Article drafts: ~/Dropbox/Scholarship/
- Committee work: ~/Documents/Faculty Service/
- Clinic materials: ~/Google Drive/Reg Policy Clinic/
- Student data: Canvas only — Claude cannot access

## What I Need Help With
- Drafting and revising article sections (especially empirical methodology descriptions)
- Creating exam questions with model answers and rubrics
- Summarizing lengthy regulatory preambles and comment letters
- Writing committee reports and faculty memos
- Organizing case law for course supplements
- Formatting Bluebook citations

## My Skill Level
- Coding: None — explain everything step by step
- Westlaw: Expert (20 years)
- Terminal: Complete beginner
- Google Docs: Comfortable
- Quantitative methods: Intermediate (can read regression tables, not run them)

## How I Prefer to Work
- Explain reasoning when suggesting changes to my writing
- Ask before modifying any files
- Match my writing voice — academic but accessible, not dry
- When discussing cases, always include full citations
- I use dictation frequently, so my prompts may be informal

## Current Projects
| Project | My Role | Current Phase |
|---------|---------|---------------|
| Agency deference article | Lead author | Revising after peer review |
| N&C rulemaking study | Co-author (empirical) | Data analysis |
| Fall Admin Law syllabus | Instructor | Updating for new cases |
| Appointments Committee report | Chair | Drafting recommendations |
```

---

## Tips

**Start minimal, then expand.** Your first version should take 20 minutes. Add detail as you discover what is useful.

**Be specific about file locations.** "I use Dropbox" is less useful than "`~/Dropbox/Scholarship/` with subfolders per article containing `/drafts/`, `/research/`, and `/notes/`."

**Include your skill level.** A beginner needs explanations; an expert wants efficiency. Do not oversell your skills -- Claude will calibrate its responses wrong.

**Update when things change.** New semester? New article project? Update your CLAUDE.md. A stale document is worse than a minimal one.

---

## Test It

After creating your CLAUDE.md, start Claude Code and ask:

> "What do you know about me and my work?"

Claude should reference information from your file. If it does not, check:

1. File location: `~/.claude/CLAUDE.md`
2. File name: Must be exactly `CLAUDE.md`
3. File contents: Open it and verify it is not empty

---

## Model Choice

Claude Code defaults to the Sonnet model, which is fast and capable for most tasks. For complex work -- long-form writing, nuanced analysis, multi-step reasoning -- consider switching to Opus:

```
/model opus
```

Claude's Opus model is more capable but uses more tokens per response (higher cost, faster usage against plan limits). This setting applies to the current session only. Switch back with `/model sonnet`.

---

## Advanced: Project-Specific CLAUDE.md

In addition to your global `~/.claude/CLAUDE.md`, you can create a CLAUDE.md in any project folder. Claude reads both when you start a session in that directory.

**How they work together:**

| File | Location | Purpose |
|------|----------|---------|
| **Global** | `~/.claude/CLAUDE.md` | Who you are -- role, preferences, contact info, working style |
| **Project** | `my-project/.claude/CLAUDE.md` | This specific project -- co-authors, tools, conventions, file paths |

Claude loads the global file first, then the project file. Project instructions can override or extend global ones.

```
article-draft/
├── .claude/
│   └── CLAUDE.md    ← project-specific instructions
├── drafts/
├── research/
└── notes/
```

This is useful when you work on multiple projects with different co-authors, citation styles, or conventions.

!!! tip "What goes in your CLAUDE.md is sent to the API"
    Everything in your CLAUDE.md files is included in every conversation with Claude Code. This is how Claude knows about you and your projects. The data is covered by Anthropic's [API data policy](https://www.anthropic.com/policies/privacy). Avoid including passwords, API keys, or information you would not want transmitted to a cloud service.

### Voice and Writing Style

If AI output never quite sounds like your writing -- too formal, too hedgy, full of words you would never use -- a voice file fixes that. It is a document that captures your actual writing patterns: sentence structure, vocabulary preferences, a ban list of AI-isms, and annotated examples.

The simplest implementation: save your core voice file to `~/.claude/rules/` and it auto-loads every session, just like other rule files. No `@import` needed for the fundamentals.

```
~/.claude/rules/core-voice.md    ← auto-loads every session
```

For context-specific registers (article voice vs. email voice vs. memo voice), load those on demand through project-level CLAUDE.md files.

For more on teaching AI your writing voice, see [Teaching AI Your Voice](../essentials/voice.md).

---

## What's Next

With your CLAUDE.md in place:

1. **[Connect external services](mcp-setup.md)** -- Give Claude access to email, docs, and calendar
2. **[Build Your Own workflows](../system/index.md)** -- Start creating custom workflows for your specific needs
