# Build Your Own

**How to create your own workflows, agents, and custom tools for legal work.**

The earlier sections taught you to use Claude Code and connect it to your services. This section teaches you to *build* -- to create custom workflows that solve your specific problems and a system that gets better the more you use it.

---

## What's Here

| Page | What You'll Learn |
|------|------------------|
| **[Your First Workflow](../workflows/first-session-skills.md)** | The prompt-plan-review-revise loop. A hands-on walkthrough of the core method. |
| **[Skills and Agents Explained](agents-vs-skills.md)** | When to use a skill vs. an agent. Architecture decisions for different tasks. |
| **[Patterns and Templates](patterns.md)** | Reusable design patterns for workflows. Quality checklist for anything you build. |

---

## The Core Idea

The most valuable thing about this system is not any individual workflow or configuration. It is the *meta-skill* of continuous improvement:

1. **Notice friction** -- Where do you do the same thing repeatedly? Where do you copy-paste between tools? Where do you lose context between sessions?
2. **Build a solution** -- Create a workflow or configure a process that handles it.
3. **Critique and iterate** -- Use Claude to review and improve what you built. (Yes, use the AI to improve the AI tools.)
4. **Share what works** -- Publish workflows that might help colleagues. Learn from what others share.

This cycle is what turns a collection of tools into a system that compounds over time. Every workflow you build makes the next one easier to build. Every pattern you learn applies to the next problem.

### What This Looks Like for Law Faculty

Here are real examples of the kind of friction you might notice -- and the workflows that solve them:

| Friction | Workflow Solution |
|----------|-------------------|
| "I spend 30 minutes at the start of each semester reformatting my syllabus" | A syllabus template workflow that updates dates, case assignments, and reading lists from a structured input |
| "I write the same type of committee memo every month" | A memo template that pulls from meeting notes and generates a first draft in your voice |
| "I lose track of where I left off on my article draft" | A session handoff workflow that captures decisions and open questions, so the next session starts with context |
| "I need to review 20 student papers and write individualized feedback" | A feedback workflow that reads each paper, checks it against a rubric, and drafts comments for your review |

---

## Prerequisites

You should have:

- A working Claude Code installation ([Install guides](../toolkit/install-mac.md))
- A configured CLAUDE.md file ([Setup guide](../toolkit/claude-md.md))
- Comfort reading and editing text files (markdown is just structured text -- not a programming language)

You do not need to know how to code. Workflows are written in markdown (structured text with simple formatting), not a programming language.

---

## Getting Started

If you are new to building workflows, start with **[Your First Workflow](../workflows/first-session-skills.md)**. It walks through the core loop -- structure your thinking, make a plan, stress-test it, execute, and capture what you learned -- using concrete examples.

If you have already worked through that and want to understand the architecture, move to **[Skills and Agents Explained](agents-vs-skills.md)** to learn when each approach is the right choice.

When you are ready to build something of your own, **[Patterns and Templates](patterns.md)** gives you the building blocks -- reusable design patterns and a quality checklist so your first custom workflow is solid from the start.
