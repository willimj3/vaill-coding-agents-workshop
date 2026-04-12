# What Agents Can Do

The best way to understand coding agents is through concrete examples. This page walks through six tasks that are common in legal work — what each one involves manually, what we tell the agent, and what happens next.

The common thread across all of them: **we describe what we want in plain English, and the agent figures out the steps.**

---

## Read and Analyze a 50-Page Contract

**The manual version:** We sit down with the document, read it cover to cover, highlight key provisions, flag unusual terms, cross-reference defined terms, note obligations and deadlines, and write up a summary. For a dense commercial contract, this can take half a day or more.

**What we tell the agent:**

> Read the contract in my Documents folder called "Acme-Widget-Supply-Agreement.pdf." Identify all payment obligations, termination provisions, non-compete clauses, and indemnification terms. Flag anything unusual compared to a standard supply agreement. Summarize your findings in a memo format with section references.

**What happens:** The agent opens the PDF, reads every page, identifies the relevant provisions, cross-references defined terms throughout the document, and produces a structured memo — complete with page and section references — in a few minutes. We review its work, verify the citations, and revise as needed.

**What it replaces:** Not our judgment. The agent does the extraction and organization. We still decide what matters, whether the unusual provisions are acceptable, and what to recommend to the client. But the hours of reading and note-taking compress into minutes of review and verification.

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

## Create a Course Syllabus from Your Notes

**The manual version:** We have scattered notes about readings we want to assign, topics we want to cover, learning objectives from a previous iteration, and timing constraints. Turning all of that into a polished syllabus means hours of organizing, formatting, writing course descriptions, and aligning everything with the academic calendar.

**What we tell the agent:**

> I am designing a 3-credit seminar on AI and Legal Ethics for the fall semester. Our semester runs August 25 to December 5, meeting Tuesdays and Thursdays at 10:00 AM. Read my notes file at "course-planning/ai-ethics-notes.md" and the previous syllabus at "syllabi/ai-ethics-2025.pdf." Create a new syllabus that incorporates the updated readings I listed in my notes, follows our law school's standard syllabus template, and includes learning objectives for each unit.

**What happens:** The agent reads both files, maps the topics to the available class sessions, incorporates the new readings while maintaining the overall structure, generates learning objectives consistent with the course goals, and produces a formatted syllabus. It flags sessions that look overloaded and suggests adjustments.

**What it replaces:** The mechanical work of assembly and formatting. The intellectual design of the course — what to teach, in what order, with what emphasis — remains ours.

---

## Review and Redline a Document

**The manual version:** A co-author or colleague sends a draft for review. We read it carefully, mark up changes, write marginal comments, and send back a redline. For a 20-page document, this can take several hours.

**What we tell the agent:**

> Read the attached draft article, "AI-Governance-Framework-Draft.docx." Review it for: (1) logical consistency — do the arguments hold together? (2) citation accuracy — flag any citations that look incorrect or incomplete, (3) clarity — identify sentences or paragraphs that are hard to follow, and (4) structural issues — does the organization serve the argument? Produce a detailed review memo with specific suggestions organized by section.

**What happens:** The agent reads the entire document, analyzes the argument structure, flags potential citation issues, identifies unclear passages, and produces a section-by-section review memo with specific, actionable suggestions. It distinguishes between substantive concerns and stylistic preferences.

**What it replaces:** The initial read-through and mechanical markup. We still bring our expertise to evaluate whether the agent's suggestions are on point, override where it is wrong, and add the substantive feedback that only a subject-matter expert can provide.

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

!!! warning "Always verify"
    None of these examples should suggest that we can hand off work to an agent and walk away. Every output requires verification. The agent can and will make mistakes — sometimes subtle ones. The [Limitations & Risks](limitations.md) page covers this in detail.
