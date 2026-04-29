# Skills vs. Agents

Claude Code has two main building blocks: **skills** (slash commands that run in the main conversation) and **agents** (subprocesses that run in a separate context). Choosing the right one matters for reliability and quality.

!!! note "Skills travel"
    Custom skills are not unique to Claude Code. They are also layer 5 of the nine-layer system Chloe Keywell describes for [Claude Cowork](../agents/cowork.md) — the same reusable workflows, used in the desktop app instead of the terminal. A skill written for one tool generally works in the other.

---

## The Key Difference

| Dimension | Skill | Agent |
|-----------|-------|-------|
| **Context** | Runs in the main conversation with full history | Runs in a fresh context -- no prior conversation |
| **User interaction** | Can ask questions, show drafts, get feedback | Returns a single result when done |
| **Memory** | Sees everything discussed so far | Sees only what you explicitly pass to it |
| **Bias** | May be influenced by prior conversation ("self-bias") | Fresh perspective -- evaluates only what is written |
| **Speed** | Instant (already in context) | Slower (starts a new process) |

---

## When to Use a Skill

Skills work best when the task:

- **Needs conversation context** -- The task builds on what you have already discussed
- **Requires user input** -- You need to answer questions or make choices mid-workflow
- **Is a multi-step workflow** -- Processes with user checkpoints along the way
- **Modifies files** -- Writing documents, updating configurations, generating drafts

**Law faculty examples:**

- **Formatting a prompt** -- You dictate a rough idea for a research question, and the skill restructures it into a well-organized prompt with role, context, task, and constraints
- **Setting up a project** -- A multi-step process that asks you questions about your course or research area and configures files based on your answers
- **Capturing session notes** -- Summarizing decisions from the current conversation so your next session starts with context

---

## When to Use an Agent

Agents work best when the task:

- **Benefits from fresh eyes** -- Review, critique, or evaluation tasks where prior context creates blind spots
- **Can run in parallel** -- Multiple evaluations or analyses that do not depend on each other
- **Needs isolation** -- You do not want the task polluting your main conversation context
- **Has a clear input and output** -- "Here is a document, give me a review" rather than "let us work through this together"

**Law faculty examples:**

- **Reviewing a brief draft** -- A fresh context evaluates the argument structure without knowing what compromises you made during drafting
- **Stress-testing a clinic proposal** -- Catches problems that the session that helped write the proposal might miss
- **Parallel research** -- Launch three agents to investigate different jurisdictions simultaneously and return independent analyses

---

## Agent Debates: Multiple Perspectives on the Same Problem

One of the most powerful uses of agents is getting them to argue with each other. Instead of a single review, you set up multiple agents with different expertise or perspectives and let them debate your plan, your draft, or your analysis.

??? example "Three reviewers critiquing a cert petition strategy"

    A faculty member was helping a clinic student draft a certiorari petition. They had a plan: lead with the circuit split, emphasize the practical consequences of the lower court ruling, and argue that the case presented a clean vehicle.

    She set up three agent personas to review the strategy:

    - **The former Supreme Court clerk** focused on vehicle problems. The case had a potential procedural defect -- the petitioner had not raised the constitutional argument below in exactly the right way. "This is the first thing the cert pool memo will flag," the agent noted.
    - **The opposing counsel** reframed the circuit split as narrower than claimed. Two of the four circuits the petition cited had distinguishable facts, and a careful respondent would argue there was no genuine conflict requiring resolution.
    - **The skeptical law professor** argued the petition buried the lead. The strongest argument was not the circuit split but an unresolved question about the standard of review. "The Court takes cases to resolve legal questions, not to pick winners in fact-bound disputes."

    Each persona saw different weaknesses. The debate produced a revised strategy that led with the standard-of-review question, addressed the vehicle problem preemptively, and narrowed the circuit split argument to the two circuits that were genuinely in conflict.

??? example "Reviewing a proposed course redesign from multiple stakeholder perspectives"

    A professor wanted to redesign a Constitutional Law course to integrate AI-assisted legal research. She set up agents as three stakeholders:

    - **The associate dean for academic affairs** flagged that the proposal did not address how AI tool access would be handled for students who could not afford subscriptions, creating an equity problem.
    - **The student** pointed out that the weekly AI exercises assumed students already knew how to use the tools. There was no onboarding -- the first exercise jumped straight to advanced prompting.
    - **The ABA site evaluator** noted that the learning outcomes did not map to any of the new technology competency requirements, missing an opportunity to demonstrate compliance.

    The three perspectives caught problems that no single reviewer would have found. The equity concern, the missing onboarding, and the accreditation alignment gap were all addressed before the proposal went to the curriculum committee.

The pattern: give agents distinct identities (methodological traditions, institutional roles, opposing perspectives) and let the disagreements surface assumptions you had not examined. The value is not in any single perspective -- it is in where they clash.

---

## The Self-Bias Problem

This is the most important reason to use agents for review tasks.

When Claude writes something in a conversation and then you ask it to review that same thing, it has a systematic bias toward finding its own work acceptable. It "knows what it meant" even if the text is ambiguous. It may not question assumptions it made earlier.

An agent running in a fresh context does not have this problem. It evaluates only what is on the page -- like handing your draft to a colleague who was not in the room when you wrote it.

**Rule of thumb:** If you are asking Claude to *critique* something it helped *create*, use an agent.

This is the same insight behind our [Stress-Test Any Plan](../workflows/plan-review-browser.md) technique -- you can apply it in a browser chatbot by simply opening a new conversation for the review.

---

## Agent File Format

Agents are markdown files saved in `~/.claude/agents/`:

```markdown
---
name: Agent Name
description: What this agent does
model: sonnet
tools:
  - Read
  - Glob
  - Grep
---

# Agent Name

[Instructions for the agent]

## Review Dimensions
[What to evaluate]

## Output Format
[How to structure the response]
```

The YAML frontmatter specifies:

- **model** -- Which Claude model to use (sonnet is cost-effective for most review tasks)
- **tools** -- Which tools the agent can access (limit to what it needs)

---

## Launching Agents

From within Claude Code:

> "Launch the brief reviewer agent on ~/Documents/cert-petition-draft.md"

Claude Code reads the agent file, starts a subprocess, passes the specified files, and returns the result to your main conversation.

You can launch multiple agents simultaneously:

> "Launch both the argument reviewer and the citation checker on this brief draft"

They run in parallel and return independent assessments.

---

## Design Guidance

| Scenario | Use | Why |
|----------|-----|-----|
| Reviewing your own draft | Agent | Avoids self-bias |
| Multi-step workflow with decisions | Skill | Needs user interaction |
| Parallel evaluations | Multiple agents | Independent fresh contexts |
| Task needs conversation history | Skill | Agent does not see prior context |
| Heavy task that would bloat context | Agent | Keeps main conversation lean |
| One-time setup or configuration | Skill | Needs to read/write files and ask questions |

The key question: **Does this task benefit from knowing the conversation history, or from not knowing it?** If the answer is "not knowing it," use an agent.
