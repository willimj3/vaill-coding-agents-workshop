# AI Project Folders: Turn Any Recurring Task into a System

<span class="badge-gold">No Claude Code required</span>

*Ready to build? [Skip to the setup](#build-your-first-file). Want to see examples first? [Jump to the examples](#see-it-in-action).*

A single file stores your stable preferences, hard constraints, and behavioral rules for a recurring domain. Every new conversation starts from that file instead of from scratch.

We use project folders for two broad categories: **legal practice tasks** (case research, contract review, client intake) and **academic work** (article writing, course prep, exam drafting). The pattern is the same -- we will walk through it using case research as the main example, then show how it applies across domains.

This works in both ChatGPT Projects and Claude.ai Projects, with minor setup differences noted below.

---

## What This Actually Looks Like

Before you invest time reading, here is the payoff in 30 seconds.

**Without a project file** -- you ask Claude to help research a regulatory question:

> *Here are the key federal regulations governing employee non-compete agreements:*
>
> *1. The FTC's proposed rule on non-compete clauses*
> *2. State-by-state analysis of enforceability*
> *3. The Restatement of Employment Law provisions*
> *4. Recent circuit court decisions on reasonableness...*

Generic. Could be for any lawyer on Earth.

**With a project file** -- same question, same chatbot:

> *Given your focus on Texas employment law, your client's industry (healthcare staffing), and the 18-month non-compete with a 50-mile radius at issue, I'd focus on three lines of analysis. Note: I'm flagging that the Texas Business & Commerce Code Section 15.50 reform from 2023 may narrow the enforceability window you've relied on in past matters. Here's a comparison of approaches with trade-offs for litigation vs. negotiated buyout...*

It references your specific constraints without you repeating them. That is the difference.

A project file is just a well-written prompt you write once and reuse for every similar matter.

---

<div class="narrative-block" markdown>
<p class="narrative-teaser" markdown>
We built our first project file for recurring case research -- the kind where you keep explaining the same jurisdictional context, the same client industry, the same analytical preferences to the AI every single time. That one file taught us the pattern we now use for everything. [See the examples below](#see-it-in-action).
</p>
</div>

---

## Build Your First File {: #build-your-first-file }

This takes about an hour for a first file, then 10 minutes to update after each use.

But before you keep reading -- open ChatGPT or Claude in another tab and think of one domain where you keep repeating yourself to the AI. Case research in a specific area, contract review for a particular client type, course preparation for a recurring seminar. Just pick one. That is what you will build.

### Platform setup

- **ChatGPT** (requires Plus or Team): Sidebar -> Projects -> New Project. Paste your instructions in the Instructions field. You can also upload reference files as **sources** -- ChatGPT draws on them in every conversation. We upload sample memos and past research as sources for case analysis; for exam drafting, the instructions alone are usually enough.
- **Claude.ai** (requires Pro): Projects -> Create Project. Paste your instructions in **Project Instructions**. You can upload reference documents to the **project knowledge** base. Claude prepends instructions to every conversation and can search the knowledge files.

Whether you need uploaded files depends on the domain. Case research benefits from source files (key statutes, leading cases, past memos). Course prep mostly needs just the instructions file. Start with instructions only and add files when you feel the gap.

### Step 1: Narrate your situation

Open a new conversation and dump everything you know about this domain. Be messy. Be thorough. Do not organize -- just talk. Even three sentences is enough to start -- the interview in Step 2 will fill the gaps.

Here is the difference between a thin dump and a useful one:

**Too thin:** *"I do employment law research."*

**Useful:** *"I research non-compete enforceability questions for healthcare clients in Texas. Most of my clients are staffing agencies with 50-200 employees. The non-competes typically have 12-24 month terms and 25-75 mile radii. I've litigated about a dozen of these in the last three years. The biggest issue is always whether the consideration is adequate under the 2011 reform act. Courts in Harris County tend to enforce narrower restrictions; Collin County is more employer-friendly. My last three winning arguments all turned on the adequacy-of-consideration prong."*

More detail = better file. Include what went wrong on past attempts, not just what went right.

### Step 2: Ask the AI to interview you

After your dump, paste this prompt:

```text
Based on what I've shared, interview me to fill in the gaps. Ask me
12 questions, one at a time, covering:

1. What is the specific legal domain and jurisdiction?
2. What types of clients or matters does this cover?
3. What are the recurring legal issues or questions?
4. What are the hard constraints (jurisdictional limits, court rules,
   filing deadlines, ethical obligations)?
5. What analytical frameworks or standards apply?
6. What past research or arguments have worked well -- and what
   specific conditions made them work?
7. What approaches have failed -- and what went wrong?
8. What is my preferred output format (memo structure, citation style,
   level of detail)?
9. What trade-offs am I usually willing to make?
10. What trade-offs am I NOT willing to make?
11. Are there any behavioral instructions for you -- things I want you
    to always do or never do when helping with this domain?
12. Is there anything I mentioned that seems contradictory or that you
    want to clarify?

Ask one question at a time. Wait for my answer before moving to the next.
```

Answer honestly. The AI is building a model of your analytical approach -- the more specific you are, the better your file will be.

!!! tip "Add failures, not just successes"
    Losses and rejected arguments are your true constraints. A legal theory that "usually works" is flexible. An argument that "was rejected by the Fifth Circuit in 2024" is a hard constraint that changes every recommendation.

!!! tip "Use explicit threshold numbers"
    "Non-competes over 24 months are presumptively unenforceable in this jurisdiction" works. "We prefer reasonable restrictions" does not. Numbers and specific standards give the AI something to actually check against.

**Checkpoint:** You should now have 10-15 specific answers. If you have fewer than 8, go back -- the thin ones are usually failures, standards, and jurisdictional nuances.

### Step 3: Ask the AI to produce a canonical file

After the interview, paste this prompt:

```text
Now synthesize everything -- my initial dump and all my interview answers -- into
a single canonical project file. Follow these rules:

1. SEPARATE stable preferences from matter-specific details. The file should
   contain only things that are true across all future uses of this domain.
   Anything specific to one case or client should be excluded.

2. USE EXPLICIT LEGAL STANDARDS, not adjectives. "Non-competes over
   24 months are presumptively unenforceable in Texas" not "we prefer
   reasonable restrictions."

3. ORGANIZE BY CATEGORY: Domain/jurisdiction, Recurring issues, Analytical
   frameworks, Preferred output format, Evidence from past matters,
   Behavioral instructions for you.

4. GIVE EACH RECURRING ISSUE its own section with both the legal standard
   AND the practical pattern from past matters.

5. FLAG anything you inferred versus what I stated directly, so I can
   correct inferences.

6. KEEP IT UNDER 500 WORDS. Shorter files produce better adherence.
   Aim for 300-500 words.

Format as clean markdown. This file will be pasted into a ChatGPT or
Claude project as standing instructions.
```

**Checkpoint:** Your file should be 300-500 words with at least one legal standard and one "past matter" lesson per category. If it is over 600 words, ask the AI to prune matter-specific details.

### Starter template

If you would rather start from a template and fill it in, here is a generic one that works for any recurring legal domain:

```text
# [DOMAIN] Research/Analysis Context

## Key Instructions
- [BEHAVIORAL RULE: e.g., "Be analytical, not agreeable. Flag weak arguments."]
- [BEHAVIORAL RULE: e.g., "Always identify adverse authority before I ask."]
- [BEHAVIORAL RULE: e.g., "Cite to specific cases and statutes, not general principles."]

## Domain & Jurisdiction
- Area of law: [specific practice area]
- Primary jurisdiction: [state/federal/both]
- Relevant courts: [specific courts or circuits]

## Recurring Legal Issues
### [Issue 1]
- Legal standard: [specific test or framework]
- Practical pattern: [what has worked in past matters]
- Watch out for: [common pitfalls]

### [Issue 2]
- Legal standard: [...]
- Practical pattern: [...]

## Hard Constraints
- [Ethical obligation or court rule]
- [Jurisdictional limit]
- [Citation format requirement]

## Preferred Output Format
- Structure: [memo format, brief section, etc.]
- Citation style: [Bluebook, local rules, etc.]
- Tone: [analytical, persuasive, advisory]

## Evidence: What Has Worked
- [Past argument/approach that succeeded] -- conditions: [why it worked]
- [Past argument/approach that succeeded] -- conditions: [why it worked]

## Evidence: What Has Not Worked
- [Past approach that failed] -- problem: [what went wrong]
- [Past approach that failed] -- problem: [what went wrong]
```

**Good fill-in:** `Non-competes over 24 months: presumptively unenforceable in TX since *Marsh USA v. Cook*, with burden shifting to employer`

**Bad fill-in:** `Non-competes: depends on the situation`

The bad version gives the AI nothing to work with. The good version gives it a standard to apply.

### How to know it is working

You are done when your file has: stable legal standards for each recurring issue, at least 2-3 explicit constraints with specific standards or thresholds, and a "what has failed" section.

**Test it:** Start a *completely new* conversation in the project (this tests whether the file actually loaded, not whether it is in your current context). Ask for analysis of a hypothetical in your domain. The hard test: the AI should flag at least one issue based on a constraint in your file that it would not know without the file. If the analysis is generically correct but not calibrated to your jurisdiction and experience, the file is not specific enough -- go back to the standards and failure patterns.

### When it does not work

**AI ignores the file.** This happens occasionally, especially in long conversations. Reprompt: "Reference my project file directly. Do not give generic analysis." Starting a fresh conversation usually fixes it.

**Generic textbook-style results.** Your file lacks specificity. The fix is almost always the same: add explicit legal standards, jurisdictional nuances, and past matter patterns. The AI defaults to generic when it does not have enough constraints to differentiate.

**File too long or bloated.** Prune to under 500 words. Remove matter-specific details (those belong in per-matter briefs, not the canonical file). Shorter files produce noticeably better adherence, especially in ChatGPT. Aim for 300-500 words after stabilization.

---

## How This Actually Develops

Do not expect your file to be good on day one. It follows a predictable arc:

**Stage 1: Messy dump -> first usable file** (conversations 1-2). Your file is rough. You update it substantially after every use. The AI's output is better than no-context conversations but still occasionally generic.

**Stage 2: Failure modes teach you the rules** (conversations 3-5). You discover what is missing -- legal standards, jurisdictional quirks, analytical preferences -- usually because the AI recommended an approach that missed a key constraint. These failures are the most productive part of the process. Each one adds a specific rule to your file.

**Stage 3: Maintenance, not building** (conversation 6+). The file is reliable enough to trust. Updates are 1-2 lines after each use, not rewrites. Your job shifts from building the file to pruning it -- removing anything matter-specific that crept in, keeping it under 500 words.

---

## See It in Action

The domain changes. The structure does not. Three examples -- from legal practice to academic work.

=== "Case Research"

    *A research folder for recurring litigation questions in a specific practice area.*

    This is the workhorse folder. We keep a standing file with the jurisdiction, the key legal standards, the analytical frameworks we prefer, and the patterns from past matters. When a new question comes up in the same practice area, the AI starts from our accumulated context instead of from zero.

    ??? note "How we actually use this"

        We use this folder in a few different modes:

        - **Deep analysis sessions** -- extended conversations working through a novel legal question. Analyzing a new circuit opinion, evaluating whether an argument that worked in one context transfers to another, mapping the implications of a statutory change.
        - **Research summaries** -- when we need to understand the current state of the law on a specific point. We ask for analysis with citations to primary authority and flag the AI's tendency to hallucinate cases.
        - **Quick lookups** -- minor procedural questions, deadline calculations, citation formatting.

        The key insight: none of this works well without the project file. Without it, you get generic legal analysis for a generic lawyer. With it, you get analysis calibrated to your jurisdiction, your courts, your practice patterns, and what has actually worked.

    **What goes in the file:** A single markdown document with your stable research context -- primary jurisdiction and relevant courts, recurring legal issues with their standards, analytical frameworks you prefer, citation format requirements, and patterns from past matters.

    **The instructions section** tells the AI how to behave:

    ```text
    ## Standing instructions
    - Always identify adverse authority before presenting analysis
    - Cite to specific cases and statutes -- not general principles
    - Flag where your analysis relies on persuasive rather than binding authority
    - When citing cases, note the year and jurisdiction
    - If you are uncertain whether a case exists, say so explicitly

    ## How to use this file
    - Reference this context at the start of any analysis
    - If my question falls outside the domain described here, tell me

    ## Citation caution
    - Never fabricate case citations
    - If asked for citations, flag them as "verify in Westlaw/Lexis"
    ```

=== "Client Intake & Compliance"

    *An instructions-only folder for recurring regulatory compliance questions.*

    This is not a research folder. It is a triage and analysis folder for recurring compliance questions in a specific regulatory domain. We keep a file with the regulatory framework, the common fact patterns, and the decision criteria for how we advise clients.

    ??? note "How we actually use this"

        We use this folder when a new compliance question arrives:

        - **Issue spotting** -- paste in the fact pattern and get an initial map of regulatory exposure areas. The file ensures the AI checks against our specific regulatory framework, not a generic compliance checklist.
        - **Memo drafting** -- generate first drafts of compliance memos with the correct structure, the right regulatory references, and our preferred analytical approach.
        - **Client communication** -- draft advisory letters that explain complex regulatory requirements in language calibrated to the client's sophistication level.

    **System instructions:**

    ```text
    You are an analytical compliance advisor, not an agreeable one.
    When reviewing a fact pattern:
    * Identify the specific regulatory provisions at issue
    * Flag the highest-risk areas first
    * Note where the facts are ambiguous and what additional
      information would change the analysis
    * Distinguish between clear violations and gray areas
    * Do not minimize risk to be reassuring
    ```

    **Building your own:** Use the same three-step process from the [setup guide above](#build-your-first-file). For compliance domains, the "hard constraints" section is especially important -- regulatory thresholds, reporting deadlines, and safe harbor conditions all need explicit numbers and dates.

=== "Course Prep & Exam Drafting"

    *A teaching-focused folder for law faculty building course materials.*

    This folder stores our teaching context: the course, the casebook, the pedagogical approach, the types of assessments we use. When we need to generate a hypothetical, draft a discussion prompt, or create an exam question, the AI starts from our specific course design.

    ??? note "How we actually use this"

        - **Exam hypotheticals** -- generate fact patterns that test specific doctrinal points at the right difficulty level. The file includes our assessment philosophy (issue-spotting vs. policy analysis) and the topics covered.
        - **Discussion prompts** -- create class discussion questions that connect to current events while staying anchored in the doctrinal framework.
        - **Syllabus updates** -- evaluate whether a new case or statutory change should replace existing course materials.

    **What goes in the file:**

    ```text
    # Constitutional Law II -- Course Context

    ## Course Parameters
    - Casebook: [specific casebook and edition]
    - Coverage: First Amendment (speech, religion, association)
    - Enrollment: 60 students, 2L/3L mix
    - Assessment: 80% final exam (4 hours, open book), 20% participation

    ## Teaching Approach
    - Socratic method with structured questions
    - Emphasis on doctrinal frameworks and their application
    - Policy analysis expected but must be grounded in doctrine
    - Students should identify the standard of review before analyzing

    ## Exam Design Preferences
    - Issue-spotting hypotheticals with 3-5 embedded issues
    - Facts should be ambiguous enough for reasonable disagreement
    - Include at least one issue where the student should identify
      that a doctrine does NOT apply
    - Avoid fact patterns that collapse into a single right answer
    ```

### Academic Work

The same principles apply to legal scholarship -- article drafting, literature reviews, grant writing, and conference presentations.

**ChatGPT Deep Research** deserves a special mention: it may be the single most valuable AI tool for law faculty doing empirical or interdisciplinary work. Give it a clear, well-engineered prompt and it produces detailed research briefings that would take hours of manual searching.

---

## Claude vs ChatGPT for This

| Dimension | ChatGPT | Claude |
|-----------|---------|--------|
| Web research | Deep Research, current case status, recent opinions | Limited |
| Structured analysis | Good | Better |
| Building the canonical file | Good | Better |
| Active case research with web sources | Better (browsing) | Good |
| Automating recurring processes | Limited | Claude Code excels |

**Our approach:** We use ChatGPT project folders for research-heavy work where we need current web information -- checking the status of pending legislation, finding recent opinions. We use Claude for structured legal analysis and building the canonical files themselves. Claude tends to produce better-organized, more precise output for analytical work. Note that ChatGPT's web browsing frequently hallucinates specific case citations, procedural postures, and holdings -- always verify against primary sources.

---

!!! tip "What We Wish We Had Known"

    - **Start with a messy dump, not a template.** Your first version will be rough. That is the process. The template above is a finishing structure, not a starting point.
    - **The file becomes reliable after about 3-4 uses.** Before that, expect to update it every time. After that, your job is maintenance, not building.
    - **Post-use updates should be 1-2 lines, not essays.** One new legal standard. One updated jurisdictional note. One "this argument worked under these conditions."
    - **Guard against the AI being too agreeable.** Specific techniques: ask it to steelman the opposing argument. Ask it to identify which of your analytical assumptions a court might reject. Ask it to generate one losing argument alongside the winners so you can see the contrast.
    - **If you edit the canonical file mid-conversation, start a new conversation afterward.** The AI has already processed the old version and may produce inconsistent results mixing old and new instructions.

---

## Next Steps

<div class="grid cards" markdown>

-   **Level up your prompts**

    ---

    The prompting techniques that make project files (and everything else) work better.

    [:octicons-arrow-right-24: Prompt Engineering](prompting.md)

-   **Understand the landscape**

    ---

    When to use ChatGPT vs Claude -- and when it matters for project folders.

    [:octicons-arrow-right-24: ChatGPT vs Claude](chatgpt-vs-claude.md)

-   **Go deeper**

    ---

    When project folders are not enough, Claude Code turns recurring tasks into automated workflows.

    [:octicons-arrow-right-24: Get Started](../setup/index.md)

</div>
