# What Agents Can Do

The best way to understand coding agents is through concrete examples. This page walks through six tasks that are common in legal and academic work — what each one involves manually, what we tell the agent, and what happens next. Each example shows something **a chatbot cannot do**: working across multiple files, executing code, accessing the web, or processing data at scale.

The common thread across all of them: **we describe what we want in plain English, and the agent figures out the steps.**

---

## Review an Entire Folder of Contracts for a Single Issue

**The manual version:** A partner asks whether any of the firm's vendor agreements contain an assignment clause triggered by a change of control — the company is being acquired and needs to know. The answer is buried across 40 contracts in a shared drive. We open each one, search for the relevant provisions, read the surrounding context, and compile a chart. A full day of work, maybe more.

**What we tell the agent:**

> Read every PDF in my "Vendor Agreements" folder. For each contract, identify whether it contains an assignment or change-of-control provision. If it does, extract the exact clause text, note whether consent is required, and flag any that would be triggered by a merger. Output a spreadsheet with columns for: vendor name, contract date, clause found (yes/no), clause text, consent required (yes/no), and any notes. Save it as "change-of-control-review.csv."

**What happens:** The agent opens all 40 PDFs, reads each one, extracts the relevant provisions, and produces a structured CSV — in minutes rather than hours. It flags contracts where the language is ambiguous or where multiple clauses interact.

**What it replaces:** The mechanical work of opening, searching, reading, and charting across dozens of files. We still interpret the clauses, decide which ones pose real risk, and advise the client. But the extraction work that would consume a full day compresses into a review task.

**Why a chatbot cannot do this:** A chatbot can analyze one document you paste in. An agent can read 40 files from your computer, process them all, and produce a structured output — without you touching any of them.

---

## Draft a Research Memo by Searching Your Files

**The manual version:** A colleague asks about our institution's policy on a specific issue. The answer is somewhere in our files — maybe in a faculty handbook PDF, maybe in meeting minutes, maybe in an email chain from last semester. We spend an hour searching, reading, and synthesizing.

**What we tell the agent:**

> Search my Faculty Senate folder and my email for anything related to the visiting scholar appointment process. I need to draft a memo summarizing the current policy, including who approves appointments, what paperwork is required, and typical timelines. Check both the official handbook and any recent emails that discuss changes.

**What happens:** The agent searches the specified folder, reads through relevant documents, scans email threads (if MCP email is connected), and produces a draft memo with citations to specific documents and messages. It flags cases where the handbook and recent practice appear to diverge.

**What it replaces:** The searching and initial synthesis. We still verify the accuracy, add our own institutional knowledge, and make the judgment calls about what to emphasize.

---

## Build a Case Tracking Spreadsheet from Email

**The manual version:** We need to create a spreadsheet tracking the status of all matters in a clinic or pro bono program. The information is scattered across dozens of email threads, intake forms, and court filing confirmations. We open each source, extract the relevant data, and enter it manually into a spreadsheet. This kind of administrative task can consume an entire afternoon.

**What we tell the agent:**

> Go through my email from the past 6 months with the subject line containing "clinic intake" or "pro bono referral." For each matter, extract the client name, matter type, date received, current status, and assigned student. Create a spreadsheet with those columns, sorted by date received.

**What happens:** The agent searches email, extracts the structured data from each message, resolves inconsistencies (such as the same matter referenced different ways in different emails), and produces a CSV or Excel file ready for review. It notes any cases where information was ambiguous or missing.

**What it replaces:** Hours of manual data entry and the inevitable errors that come with it. We review the spreadsheet for accuracy, fill in gaps the agent flagged, and have a working tracking system.

---

## Collect and Code Data from Public Filings at Scale

**The manual version:** An empirical research project requires coding governance variables from SEC filings — hundreds of IPO prospectuses and proxy statements. Student RAs download each filing from EDGAR, read through it, extract the relevant provisions, and enter coded variables into a spreadsheet. For 844 firms, this takes a team of RAs an entire semester.

**What we tell the agent:**

> Here is a CSV with 844 firm names and CIK identifiers. For each firm, go to SEC EDGAR, download the IPO prospectus (Form 424B4) and all available proxy statements (DEF 14A). From each filing, extract and code: board size, whether the firm has a classified board, whether it has a dual-class share structure, and the voting threshold for charter amendments. Save the coded data as a CSV. Log every filing URL you accessed.

**What happens:** The agent builds a pipeline: it looks up each firm on EDGAR, downloads the filings, extracts the relevant sections, codes the variables using consistent rules, and produces a structured dataset — with a log of every source. Work that took a team months compresses into hours.

**What it replaces:** The mechanical labor of downloading, reading, extracting, and coding across hundreds of filings. We still design the codebook, validate the output against hand-coded samples, and interpret the results. But the data collection bottleneck — the part that limits the scale of empirical legal research — largely disappears.

**Why a chatbot cannot do this:** A chatbot cannot access EDGAR, download filings, or process hundreds of documents sequentially. An agent can execute the entire pipeline — web access, file downloads, text extraction, coding, and output — in a single workflow.

---

## Replicate a Published Paper's Results from Its Data Archive

**The manual version:** A co-author wants to build on a published empirical paper. Before extending it, we need to verify we can reproduce the original results. We download the replication archive, figure out which data files map to which tables, translate the original code (often in Stata or R) into our preferred language, run the regressions, and compare. This can take days of debugging.

**What we tell the agent:**

> Download the replication archive from this repository URL. Read the paper at "papers/thompson-et-al-2020.pdf." Identify the main analysis dataset and replicate Tables 2 and 3. Compare your estimates to the published values and flag any discrepancies. Use Python with statsmodels. Show me the code and results for each table before proceeding.

**What happens:** The agent downloads the archive, reads the paper to understand the analysis, identifies the correct data files, translates the statistical specifications into Python, runs the regressions, and reports whether the results match — all in minutes rather than days. It flags discrepancies and explains possible causes.

**What it replaces:** The tedious work of code translation, data wrangling, and debugging that makes replication studies so time-consuming. We still decide whether discrepancies are meaningful, evaluate the methodology, and design the extension.

**Why a chatbot cannot do this:** A chatbot cannot download files from a repository, open and inspect data archives, write and execute code, or compare numerical output against published tables. An agent does all of this in a continuous workflow.

---

## Automate Client Intake Forms

**The manual version:** We receive unstructured information from potential clients — phone messages, emails, walk-in notes — and need to enter it into a standardized intake form. Each entry requires reading the source material, extracting relevant facts, and populating the correct fields. In a clinic setting with dozens of intakes per semester, this is a significant time investment.

**What we tell the agent:**

> Read the email thread from Maria Lopez received yesterday about a landlord-tenant dispute. Extract all relevant intake information: client name, contact information, opposing party, nature of dispute, key dates, and relevant facts. Fill in our standard clinic intake template (the one at "templates/intake-form-template.md") and flag any information that is missing or unclear.

**What happens:** The agent reads the email thread, identifies the relevant facts, maps them to the template fields, fills in what it can, and clearly marks fields where information is missing or ambiguous — along with a note about what to ask in the follow-up call.

**What it replaces:** The clerical work of extraction and data entry. The substantive evaluation of the matter — whether we can take the case, what legal issues are present, what our initial strategy should be — is still entirely ours.

---

## The Pattern

Notice what is consistent across all six examples:

1. **We describe the task in plain English.** No code, no special syntax, no technical knowledge required.
2. **The agent handles the mechanical work.** Reading, searching, extracting, organizing, formatting.
3. **We provide the judgment.** Verifying accuracy, making substantive decisions, applying expertise.
4. **The result is a starting point, not a final product.** Every output needs human review and refinement.

This division of labor — agent handles volume and mechanics, human provides judgment and expertise — is the fundamental pattern of productive agent use. It does not replace legal reasoning. It frees up time and attention for more of it.

---

## Real-World Examples from Academia

The examples above are hypothetical. These are not. A growing number of academics are using coding agents in their research and documenting what works and what does not.

### Replicating and extending a published paper in under an hour

**Andy Hall** (Stanford GSB) gave Claude Code a single prompt: replicate and extend a published empirical paper on vote-by-mail policy (Thompson et al. 2020, *Proceedings of the National Academy of Sciences*). With minimal oversight, Claude Code downloaded the replication data, **reproduced the published estimates exactly**, collected new data across three states for 2020-2024 with high accuracy (29/30 counties correct), and ran the extended analysis — producing results nearly identical to the independent human replication.

An independent audit by Graham Straus (UCLA) also found real limitations: Claude missed gubernatorial and senatorial data for two states, produced lower-quality work when going beyond the original methodology, and failed to keep adequate records of its decisions.

*"While it's clear to us that AI agents require expert oversight to accurately produce new papers, it is also clear to us that this constitutes a major potential change to how empirical research will be conducted moving forward."*

[:octicons-arrow-right-24: Read the full audit (PDF)](../papers/Straus_Hall_Claude_Audit.pdf){ target="_blank" } — Straus and Hall, January 2026

### Converting a method into a research-ready R package in one day

**Solomon Messing and Joshua Tucker** (NYU) used coding agents to convert a minimal statistical method implementation into a fully functional, modular, and well-documented R package — in just over one day. They also produced a 20-page empirical analysis of corporate responses to Russia's 2022 invasion, complete with data visualizations and statistical analyses, in under an hour. Their Brookings essay argues that coding agents represent a transformative moment for social science, comparable to the introduction of statistical software itself.

[:octicons-arrow-right-24: Read "The Train Has Left the Station"](https://www.brookings.edu/articles/the-train-has-left-the-station-agentic-ai-and-the-future-of-social-science-research/){ target="_blank" } — Brookings, March 2026

### Reproducing economics findings by converting Stata to Python

**Ethan Mollick** (Wharton) gave Claude Code a sophisticated economics paper along with its replication data archive. Claude read the paper, opened the archive, sorted through the files, converted the statistical code from Stata to Python, and methodically reproduced the findings — all without manual intervention. Mollick has written extensively that coding agents represent a capability leap, not an incremental improvement, and that academics who ignore them risk falling behind.

[:octicons-arrow-right-24: Read "Claude Code and What Comes Next"](https://www.oneusefulthing.org/p/claude-code-and-what-comes-next){ target="_blank" } — One Useful Thing, 2025

### Building a full academic research workflow

**Pedro Sant'Anna** (Emory, Economics) published a detailed Claude Code workflow covering the entire academic research pipeline: manuscript drafting, data analysis in R, literature synthesis, presentation creation, and replication packages. His system uses 14 specialized agents for tasks like peer review simulation, adversarial quality checking, and proofreading. It has been adopted by 15+ research groups across economics, political science, energy, and engineering.

[:octicons-arrow-right-24: See the workflow](https://psantanna.com/claude-code-my-workflow/){ target="_blank" } — Sant'Anna, 2026

### Switching an entire empirical practice to coding agents

**Scott Cunningham** (Baylor, Economics), author of *Causal Inference: The Mixtape*, documented his complete switch to Claude Code for empirical econometrics. His series describes how coding agents changed not just his efficiency but the way he approaches research problems — from data cleaning to analysis to visualization. His verdict: "I'm never going back."

[:octicons-arrow-right-24: Read "Claude Code Changed How I Work"](https://causalinf.substack.com/p/claude-code-changed-how-i-work-part){ target="_blank" } — Causal Inference Substack, 2026

### AI workflows for professionals who don't code

**Chris Blattman** (U Chicago, Political Economy) built an open-source AI workflow system for managing academic research, writing, and course design — all designed for professionals without a coding background. His site demonstrates how to organize AI tools around the work academics actually do. It is the project this guide was originally adapted from.

[:octicons-arrow-right-24: Visit claudeblattman.com](https://claudeblattman.com/){ target="_blank" }

---

!!! warning "Always verify"
    None of these examples should suggest that we can hand off work to an agent and walk away. Every output requires verification. The agent can and will make mistakes — sometimes subtle ones. The [Limitations & Risks](limitations.md) page covers this in detail.
