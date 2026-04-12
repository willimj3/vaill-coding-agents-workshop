# For Legal Practice

**AI workflows for the work lawyers actually do -- contracts, briefs, research, communication, and document analysis.**

---

## Why This Section Exists

Most AI-for-lawyers guidance falls into two camps: breathless enthusiasm ("AI will transform everything!") or dire warnings ("AI will ruin your career!"). Neither is particularly helpful when you are sitting at your desk on a Tuesday afternoon trying to figure out whether a non-disclosure agreement is missing a carve-out.

This section takes a different approach. We walk through five common legal workflows, show where AI can genuinely help, and flag where it cannot. Every page includes concrete prompts you can try today, configuration files you can adapt to your practice, and ethical guardrails grounded in the ABA Model Rules.

The goal is not to replace your legal judgment. It is to free up more of your time *for* legal judgment by offloading the mechanical parts of legal work -- the first-pass review, the initial draft, the document summary -- to a tool that handles them well enough to be useful, as long as you verify everything it produces.

---

## What We Cover

<div class="grid cards" markdown>

-   **:material-file-document-check-outline: Contract Review**

    ---

    Using AI to review contracts for key clauses, missing provisions, and non-standard terms. Includes a CLAUDE.md template for contract review and a practical always-verify checklist.

    [:octicons-arrow-right-24: Read more](contract-review.md)

-   **:material-scale-balance: Brief Drafting**

    ---

    Integrating AI into the brief-writing workflow -- from research through drafting to cite-checking. Covers IRAC-structured prompting and the critical importance of verifying every citation.

    [:octicons-arrow-right-24: Read more](brief-drafting.md)

-   **:material-book-search-outline: Legal Research**

    ---

    AI-assisted legal research: what it can do, what it cannot, and how to combine it with traditional research tools. Includes a comparison table and guidance on MCP document connections.

    [:octicons-arrow-right-24: Read more](legal-research.md)

-   **:material-email-edit-outline: Client Communication**

    ---

    Drafting client letters, status updates, and engagement letters with AI assistance. Covers confidentiality considerations, voice files for client-facing writing, and templates for recurring communications.

    [:octicons-arrow-right-24: Read more](client-communication.md)

-   **:material-file-find-outline: Document Analysis**

    ---

    Analyzing large document sets -- discovery materials, due diligence files, regulatory filings -- using Claude Code's ability to read files directly from your computer. Privacy considerations and practical examples.

    [:octicons-arrow-right-24: Read more](document-analysis.md)

</div>

---

## A Note on Professional Responsibility

Every page in this section includes ethics considerations specific to that workflow. But a few principles apply everywhere:

**Competence (Model Rule 1.1).** The duty of competence includes understanding the tools you use. You do not need to understand how a large language model works at a technical level, but you do need to understand what it is good at, where it fails, and why human verification is non-negotiable. Reading this section is a step toward that understanding.

**Confidentiality (Model Rule 1.6).** Client information entered into a consumer AI product may be used for training, logged by the provider, or otherwise exposed. We address this on every page, but the short version: be deliberate about what information you share with AI tools, use local processing options (like Claude Code running on your own machine) for sensitive work, and review your AI provider's data handling policies.

**Supervision (Model Rules 5.1 and 5.3).** AI output requires the same level of review you would give to work produced by a junior associate. This means reading every word, verifying every citation, and applying your own judgment to every conclusion. "The AI wrote it" is not a defense to a malpractice claim.

**Candor (Model Rule 3.3).** If AI-generated content contains errors -- particularly fabricated citations -- and you submit it to a tribunal without catching those errors, you have a candor problem. The brief-drafting and legal research pages address this directly.

---

## How to Use These Pages

Each page follows a consistent structure:

1. **What AI does well** in this workflow
2. **Step-by-step instructions** with example prompts
3. **Configuration files** (CLAUDE.md templates, voice files, project folder structures)
4. **Limitations and failure modes** -- where the AI will get things wrong
5. **Ethical considerations** specific to the workflow
6. **A verification checklist** -- what to check before relying on AI output

We recommend reading the pages in order the first time through, since later pages build on concepts introduced earlier. After that, use them as reference material for your daily work.

---

## Prerequisites

These pages assume you have:

- A paid subscription to Claude (Pro or Max) or ChatGPT (Plus or Pro)
- Basic familiarity with prompting (covered in [Prompt Engineering](../essentials/prompting.md))
- For the more advanced workflows: Claude Code installed ([Mac](../toolkit/install-mac.md) | [Windows](../toolkit/install-windows.md))

You do not need any coding experience. Where we reference Claude Code features, we explain them in plain terms.

---

## The Fundamental Rule

Every page in this section comes back to the same principle:

!!! warning "AI augments. It does not replace."

    Use AI to produce a first draft, a preliminary analysis, or a structured summary. Then apply your training, your experience, and your judgment. The lawyer is always responsible for the final work product. Always.

This is not a limitation of AI that will be solved by the next model release. It is the nature of legal work. Legal judgment requires understanding context, relationships, strategy, and consequences that AI does not have access to. What AI gives you is speed on the mechanical parts, so you have more time for the parts that require a lawyer.
