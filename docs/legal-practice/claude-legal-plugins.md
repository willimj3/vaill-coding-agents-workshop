# Claude Legal Plugins

<span class="badge-gold">Claude Code & Cowork</span>

In May 2026, Anthropic released [**claude-for-legal**](https://github.com/anthropics/claude-for-legal) — an open-source suite of practice-area plugins for Claude Code and Cowork, built specifically for legal workflows. Twelve plugins, more than eighty specialized agents, and around twenty MCP connectors for legal tools like DocuSign, LexisNexis, Thomson Reuters, and Everlaw.

This page is a brief orientation. We expect to cover the plugins in more depth as we use them in our own practice and teaching — for now, the goal is to make you aware that they exist and to help you decide whether to install one.

!!! note "Why this matters"

    Until very recently, getting Claude Code to behave like a legal-domain assistant required writing your own `CLAUDE.md`, voice files, and prompt templates — most of what the rest of this site walks you through. The plugins do not replace that work, but they give you a credible starting point with built-in guardrails around privilege, citation, and jurisdiction. If you have been hesitant to set up your own configuration from scratch, a relevant plugin is a sensible first step.

---

## What's in the Suite

The repository ships twelve plugins. You install only the ones that match your practice; each is a self-contained set of skills, agents, and prompts.

| Plugin | Designed For |
|--------|--------------|
| **commercial-legal** | Vendor and NDA review, SaaS agreements, amendment tracing, renewal tracking |
| **corporate-legal** | M&A diligence, closing checklists, board consents, entity compliance |
| **employment-legal** | Hire and termination review, worker classification, leave tracking, investigations |
| **privacy-legal** | DPA review, data-subject access requests, privacy impact assessments |
| **product-legal** | Launch review, marketing claims checking, feature risk assessment |
| **regulatory-legal** | Regulatory feed monitoring, policy diff, gap tracking, NPRM comments |
| **ai-governance-legal** | AI use-case triage, impact assessments, vendor AI review |
| **ip-legal** | Trademark clearance, freedom-to-operate triage, cease-and-desist drafting |
| **litigation-legal** | Matter intake, claim charts, deposition prep, privilege logs, docket watching |
| **legal-clinic** | Law school clinic setup, student onboarding, intake, deadline tracking |
| **law-student** | Socratic drilling, case briefing, IRAC grading, bar prep |
| **legal-builder-hub** | Community skill discovery and installation with trust checks |

The **legal-clinic** and **law-student** plugins are particularly relevant for legal academia — the rest of the site is broadly applicable to academic work, but those two are built explicitly for it.

---

## How They Work

Each plugin is built around three ideas that mirror what we teach throughout this guide:

1. **A cold-start interview.** When you first install a plugin, you run a `cold-start-interview` skill that asks about your practice — your jurisdiction, your escalation rules, your house style. This takes 10 to 20 minutes and produces a `CLAUDE.md` practice profile that every other skill in the plugin reads from.

2. **Skills, not chat.** Each plugin contains many small, well-scoped skills — e.g., `triage-nda`, `review-contract`, `legal-risk-assessment`. You invoke them by name (`/legal:triage-nda`) and they return a structured deliverable rather than free-form conversation.

3. **Guardrails built in.** The plugins are designed around the assumption that **every output is a draft for attorney review**. Source attribution is required on citations, conservative defaults are used for privilege calls, jurisdiction assumptions are surfaced explicitly, and there are explicit gates before anything is filed or sent.

This is the same architecture we describe in the [Build Your Own](../system/index.md) section — Anthropic has simply done a great deal of the configuration work for you.

---

## Installing a Plugin

Detailed install instructions live in [the repository's QUICKSTART](https://github.com/anthropics/claude-for-legal/blob/main/QUICKSTART.md), but the short version:

1. Make sure Claude Code is installed and working ([Mac](../toolkit/install-mac.md) or [Windows](../toolkit/install-windows.md)).
2. Clone or download the repository.
3. In Claude Code, run `/plugin marketplace add ` (with a trailing space), drag the unzipped folder onto the terminal window, and press Enter.
4. Install the specific plugin you want with `/plugin install <plugin-name>`.
5. Run the cold-start interview for that plugin and answer the questions about your practice.

The plugins are MIT-licensed and free. You do still need a paid Claude subscription (Pro or Max) to run them.

---

## Honest Considerations

- **Still very new.** The suite launched in May 2026. Real-world testing across diverse practice areas is just beginning. Treat early outputs with the same skepticism you would apply to a new associate's first draft.
- **Connectors are optional but powerful.** Several skills work without any MCP connectors configured, but they reach their full potential when wired to a research tool (CourtListener, Trellis, Descrybe, Solve Intelligence) and to your firm or institutional systems (Google Drive, DocuSign, your DMS).
- **Practice profile matters.** The cold-start interview is not a formality — the same plugin behaves quite differently depending on what you tell it about your jurisdiction, your tolerance for ambiguity, and your escalation rules. Take the time to answer carefully.
- **None of this changes the fundamental rule.** AI augments. It does not replace. The professional-responsibility considerations in [the section index](index.md) apply to plugin output exactly as they apply to anything else Claude produces.

---

## Going Deeper

A more detailed walk-through of the plugins — what each one does in practice, what we have found useful, where the rough edges are — is coming. In the meantime:

- [**anthropics/claude-for-legal**](https://github.com/anthropics/claude-for-legal) — the official repository
- [**Claude for the legal industry**](https://claude.com/blog/claude-for-the-legal-industry) — Anthropic's launch announcement
- [**Anthropic Goes All-In on Legal**](https://www.lawnext.com/2026/05/anthropic-goes-all-in-on-legal-releasing-more-than-20-connectors-and-12-practice-area-plugins-for-claude.html) — LawSites coverage with practical context

If you try one of the plugins and have observations to share, we'd love to hear from you — see the [Resources](../resources.md) page for ways to get in touch with the lab.
