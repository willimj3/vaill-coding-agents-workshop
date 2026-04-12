# Grant Writing

**Using AI to draft proposals, budget narratives, and methodology sections. Stress-test your application before submission. Adapt your tone for different funders.**

Grant writing is one of the most high-stakes writing tasks in academia. The difference between funding and rejection often comes down to clarity, persuasion, and fit with the funder's priorities — not the quality of the underlying idea. AI is remarkably useful here: it can produce clean first drafts, tighten prose, restructure arguments, calculate budgets, and — most valuably — play the role of a skeptical reviewer before you submit.

!!! tip "The highest-value technique on this page"
    The single most useful thing AI can do for grant writing is **stress-test your proposal before you submit it.** Paste your near-final draft into a fresh chat and ask the AI to act as a skeptical reviewer. This is the [plan review technique](../workflows/plan-review-browser.md) applied to grant writing, and it consistently catches problems that the author is too close to the work to see. [Jump to that section.](#stress-testing-your-proposal)

---

## Why This Matters

Most law faculty were not trained to write grants. Legal scholarship typically does not require external funding — you write an article, submit it to a journal, and the process costs you nothing but time. But empirical legal research, interdisciplinary projects, and clinical programs increasingly depend on grant funding, and the proposal-writing process is unlike any other form of legal writing.

Grant proposals must simultaneously:

- Explain the problem in terms the funder cares about
- Demonstrate that your approach is methodologically sound
- Convince reviewers that you can execute the project
- Present a realistic budget and timeline
- Stand out among dozens or hundreds of competing proposals

AI helps at every stage. It does not replace the intellectual core — your idea, your expertise, your institutional context — but it accelerates the writing, sharpens the argument, and catches weaknesses before reviewers do.

---

## The Workflow

### Step 1: Build a grant writing project folder

If you write grants regularly, create a project folder with standing instructions that apply to all your proposals. Per-grant details go into individual conversations.

```text
# Grant Writing

## About me
I am a [title] at [institution]. My research focuses on [areas].
I have previously received funding from [funders, if applicable].

## My writing voice for grants
- Persuasive but evidence-based — make strong claims, back them
  with citations and data
- Specific and concrete — name the intervention, quantify the
  impact, describe the mechanism
- Accessible to reviewers who are not specialists in my sub-field
- Short paragraphs, active voice, minimal jargon

## How to help me
- Draft sections to my specifications and maintain my voice
- When I paste a draft, identify weaknesses a reviewer would
  flag — be direct, not diplomatic
- Help me translate technical concepts for non-specialist
  reviewers
- When calculating budgets, show your math and flag any
  assumptions

## Rules
- Never invent citations or statistics — if you are unsure,
  say so
- Do not use filler language ("this innovative and impactful
  project") — every sentence should carry information
- When I ask you to review a draft, start with the weaknesses,
  not the strengths
- Flag any claim that needs a citation but does not have one
```

This is your voice file for grant writing — the AI equivalent of the [voice file](../essentials/voice.md) technique, tailored for persuasive evidence-based prose.

### Step 2: Outline before drafting

Do not ask the AI to draft a complete proposal in one pass. Start with an outline and get the structure right before writing prose.

```text
I am applying to [funder] for a [type of grant: research grant /
program grant / fellowship]. The deadline is [date]. Maximum budget
is [amount] over [period].

Here is my project in one paragraph:
[Describe your project — the problem, the approach, the expected
contribution]

The proposal requires these sections:
[List the sections from the funder's guidelines]

Draft an outline for each section. For each, include:
1. The key argument or information that section must convey
2. Approximate word count (the total proposal is limited to
   [N] pages)
3. What evidence or citations I will need to include
4. How this section connects to the ones before and after it

Before you draft the outline, identify the 3 most important things
this proposal must convince reviewers of. Structure everything
around those three points.
```

### Step 3: Draft section by section

With the outline approved, draft one section at a time. This gives you the chance to course-correct before the AI builds on weak foundations.

```text
Draft the methodology section based on the outline above.

Requirements:
- 800-1000 words
- Describe the research design, data sources, and analytical
  approach in enough detail that a reviewer can evaluate
  feasibility
- Address potential threats to validity and explain how the
  design mitigates them
- Include placeholders like [CITE] where I need to add specific
  citations — do not invent them
- Maintain the persuasive-but-evidence-based tone from my
  project file

Audience: Reviewers are social scientists and legal scholars. They
understand research methods but may not be experts in [your
specific area]. Do not assume familiarity with [specific
methodological terms] without brief explanation.
```

### Step 4: Adapt tone for different funders

Different funders have different cultures. An NSF proposal reads differently from a foundation proposal, which reads differently from an internal university grant. AI can help you calibrate.

```text
I have a draft methodology section written for an NSF proposal.
I need to adapt it for a [foundation name] proposal. Key differences:

- NSF reviewers expect technical precision and methodological rigor.
  [Foundation] reviewers prioritize real-world impact and
  accessibility.
- NSF proposals can assume methodological literacy.
  [Foundation] proposals should explain methods in plain language.
- NSF tone is scholarly and formal.
  [Foundation] tone is still evidence-based but warmer and more
  narrative.

Rewrite the section for [Foundation]. Keep all the substantive
content but adjust the tone, level of technical detail, and
emphasis. Where the NSF version leads with methods, the
[Foundation] version should lead with impact.
```

### Step 5: Budget and timeline

AI is useful for the mechanical aspects of budget preparation — calculating personnel costs, estimating travel, and building timeline charts.

```text
Help me build a budget for a 3-year research project. Here are
the components:

Personnel:
- PI (me): 1 month summer salary per year at [rate]
- Postdoc: full-time, 12 months per year at [rate]
- 2 research assistants: 10 hours/week each during academic year,
  20 hours/week during summer, at [rate]

Travel:
- 2 domestic conference trips per year (airfare, 3 nights hotel,
  per diem)
- 4 field site visits per year (driving distance, no flights,
  1 night hotel, per diem)

Other direct costs:
- Survey platform subscription: [amount]/year
- Data acquisition from [source]: [amount] one-time
- Publication fees: [amount] for 2 articles over the grant period

Fringe benefits rate: [percentage]
Indirect cost rate: [percentage]

Build a year-by-year budget table. Include a 3% annual escalation
for salaries. Show subtotals for each category and a grand total.
Flag if the total exceeds the funder's maximum of [amount].
```

---

## Stress-Testing Your Proposal

This is the most valuable section on this page. Before you submit, paste your near-final proposal into a fresh chat (not your project folder — you want a reviewer's perspective, not a collaborator's).

```text
You are a skeptical but fair grant reviewer evaluating a proposal
for [funder]. You serve on the review panel for [program name].
You have reviewed hundreds of proposals and funded fewer than 20%
of them.

Here is the proposal:

[Paste your full proposal]

Review this proposal as you would for a real panel. Address:

1. SIGNIFICANCE: Is the problem important? Does the proposal
   make a convincing case for why this matters? What is the
   strongest competing priority that might outweigh this project
   in a reviewer's mind?

2. APPROACH: Is the methodology sound? What are the weakest
   points in the research design? What would a methods expert
   challenge?

3. FEASIBILITY: Is the timeline realistic? Is the budget
   appropriate? Does the applicant have the track record to
   execute this?

4. CLARITY: Is the proposal clearly written? Where did you have
   to re-read a sentence to understand it? Where is the argument
   structure weak?

5. FIT: Does this proposal align with [funder]'s stated
   priorities? Where is the alignment strongest and weakest?

6. OVERALL: If you had to rank this proposal in the top 20%,
   middle 40%, or bottom 40%, where would it fall and why?

Be direct. I need to hear the problems now, not after submission.
Score each section on a 1-5 scale and explain the score.
```

Run this review twice — once in ChatGPT and once in Claude. The models have different analytical styles and will catch different problems. Compare the reviews and address the issues that both models flag.

---

## CLAUDE.md Template for Grant Writing Projects

If you are using Claude Code for a grant project, put a CLAUDE.md file in the project directory:

```markdown
# Grant Project: [Title]

## Funder
[Name, program, deadline, maximum budget]

## Project summary
[One paragraph describing the project]

## File structure
- drafts/ — current working drafts of each section
- final/ — submission-ready documents
- budget/ — budget spreadsheets and calculations
- references/ — bibliography and supporting documents
- reviews/ — feedback from colleagues and AI reviews

## Writing conventions
- Voice: Persuasive, evidence-based, accessible to non-specialists
- Format: Follow [funder]'s formatting requirements exactly
- Citations: Use [citation format]. Mark unverified citations
  with [CITE-NEEDED]
- Length limits: [Specify per-section limits from funder guidelines]

## Rules
- Never invent statistics, citations, or institutional details
- When drafting, include [CITE] placeholders rather than
  fabricating references
- Flag any claim that needs supporting evidence but does not have it
- When I ask for a review, prioritize weaknesses over strengths
- Before finalizing any section, check it against the funder's
  evaluation criteria
```

---

## Limitations

**AI does not know your institution.** It cannot accurately describe your facilities, your collaborators' qualifications, or your institutional context. Those details must come from you.

**Funder-specific requirements change.** AI may not have current information about a funder's priorities, formatting requirements, or evaluation criteria. Always work from the funder's current guidelines, not the AI's memory of past cycles.

**Budget calculations need verification.** AI is generally reliable for arithmetic, but fringe benefit rates, indirect cost rates, and escalation calculations should be verified against your institution's sponsored programs office numbers.

**Over-polished prose.** AI grant drafts can sound too smooth — the "innovative and impactful" register that reviewers associate with empty marketing. Edit aggressively for substance over polish. Every sentence should carry information that helps the reviewer evaluate your proposal.

**AI cannot replace relationships.** The best grant writing advice often comes from program officers, successful applicants, and colleagues who have served on review panels. AI can help you draft and refine, but it cannot replace the human network that makes grant writing successful.

---

## Practical Tips

!!! tip "The 'so what' test"
    After drafting each section, ask the AI: "Read this section and tell me, in one sentence, what the reviewer will take away from it. If that sentence does not match what I intended, tell me where the gap is." This catches sections that are technically accurate but fail to communicate their core point.

!!! tip "Recycling across proposals"
    Your project folder accumulates reusable components — biographical sketch language, methodology descriptions, institutional context paragraphs. Ask the AI to maintain a library of these components so you can assemble future proposals faster. Tag each component with the funder and date so you know what to update.

---

## Next Steps

<div class="grid cards" markdown>

-   **Master the plan review technique**

    ---

    The stress-testing approach works for any plan, not just grants.

    [:octicons-arrow-right-24: Stress-Test Any Plan](../workflows/plan-review-browser.md)

-   **Build your writing voice file**

    ---

    A voice file for grant writing ensures the AI drafts in your style, not its default register.

    [:octicons-arrow-right-24: Teaching AI Your Voice](../essentials/voice.md)

-   **Set up project folders**

    ---

    The project folder technique keeps your grant writing context persistent across conversations.

    [:octicons-arrow-right-24: AI Project Folders](../essentials/project-folders.md)

</div>
