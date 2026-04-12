# VAILL Coding Agents Workshop

**A hands-on workshop for law faculty — from AI chatbots to coding agents with Claude Code.**

Website: [willimj3.github.io/vaill-coding-agents-workshop](https://willimj3.github.io/vaill-coding-agents-workshop/)

## About

This site supports the Vanderbilt AI Law Lab (VAILL) Coding Agents Workshop, a 5-session program designed for law faculty with little to no coding experience. It covers:

- **AI Essentials** — Chatbot best practices, prompt engineering, and AI project management (no installation required)
- **What Are Coding Agents?** — Understanding the landscape of AI coding tools and what they can do for legal professionals
- **Setup** — Step-by-step installation of Claude Code on Mac and Windows
- **For Legal Practice** — Contract review, brief drafting, legal research, client communication, and document analysis
- **For Legal Academia** — Literature reviews, empirical research, course design, exam drafting, grant writing, and student feedback
- **Build Your Own** — Creating custom workflows and automation patterns

## Workshop Structure

| Session | Focus | Prerequisites |
|---------|-------|---------------|
| Pre-work | Home, Chatbots, Prompting, Cost | None |
| Session 1 | Voice, Project Folders, Plan Review | Browser only |
| Session 2 | What Are Coding Agents? | Conceptual |
| Session 3 | Install, CLAUDE.md, MCP | Laptop required |
| Session 4 | Legal Practice + Legal Academia | Claude Code installed |
| Session 5 | Build Your Own workflows | Claude Code installed |

## Local Development

```bash
pip install -r requirements.txt
mkdocs serve
```

Open [localhost:8000](http://localhost:8000) to preview.

## Deployment

The site auto-deploys to GitHub Pages on every push to `main` via GitHub Actions.

## Credits

Adapted from the [claudeblattman](https://github.com/chrisblattman/claudeblattman) open-source project by Chris Blattman. Built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/).

## License

MIT
