# Student Feedback

**Using AI to provide structured, rubric-based feedback on student writing — while respecting privacy boundaries and knowing when personal feedback matters more.**

Giving detailed feedback on student writing is one of the most impactful things law faculty do. It is also one of the most time-consuming. A thoughtful set of comments on a single legal memorandum can take 30 to 45 minutes. Multiply that by 60 or 80 students and the math becomes punishing. Faculty face a constant trade-off: depth of feedback versus number of students who receive it.

AI changes that math. It can produce structured, rubric-based feedback on student drafts in minutes — feedback that is detailed, consistent, and tied to specific passages in the text. That does not mean we hand off the feedback process entirely. It means we use AI to generate a first-pass analysis that we then review, refine, and personalize before returning it to the student. The AI handles the structural evaluation; we add the pedagogical judgment, the encouragement, and the course-correction that only a human instructor can provide.

!!! danger "The privacy rule: no exceptions"
    **Never input student names, student IDs, institutional email addresses, grades, or any other personally identifiable information into any AI tool.** This is not merely a best practice — it implicates FERPA obligations and your institution's data governance policies. Remove all identifying information before pasting student work into a chatbot. See the [full privacy section below](#privacy-and-ferpa-considerations) for specifics.

---

## Why This Matters

Feedback quality is one of the strongest predictors of student learning in legal education. Students who receive specific, actionable feedback on their writing improve faster than students who receive generic praise or unexplained grades. But the bottleneck is not willingness — most law faculty want to give better feedback. The bottleneck is time.

AI addresses the time bottleneck without sacrificing quality if we use it correctly. The key is treating AI feedback as a scaffold that we build on, not a finished product we hand off. The AI can:

- Evaluate whether a student's analysis follows IRAC/CREAC structure
- Identify passages where the rule statement is missing or incomplete
- Flag conclusory analysis that lacks application of facts to law
- Check whether counterarguments are addressed
- Evaluate organization, transitions, and paragraph structure
- Compare performance across rubric dimensions
- Identify patterns in common errors across multiple submissions

What the AI cannot do: understand why this particular student is struggling, know that a student is dealing with a difficult personal situation, calibrate encouragement for a student who lacks confidence, or exercise the pedagogical judgment about what this student needs to hear right now. Those are human tasks, and they are the most important part of feedback.

---

## The Workflow

### Step 1: Create a feedback voice file

Before generating any feedback, define the tone and approach you want the AI to use. This is a [voice file](../essentials/voice.md) specifically calibrated for constructive academic feedback.

```text
# Feedback Voice

## Tone
- Constructive and encouraging, but honest about weaknesses
- Direct about what needs improvement — do not bury criticism
  in compliments
- Specific: reference particular passages, sentences, or
  paragraphs by quoting them
- Frame weaknesses as opportunities for growth, not as failures

## Structure
For each piece of feedback:
1. Start with what the student did well — be specific
   (not "good job" but "your rule statement on page 2 clearly
   articulates the three-part test")
2. Identify areas for improvement — tied to specific passages
3. Explain why the improvement matters — connect to the
   analytical skill being developed
4. Suggest a concrete next step the student can take

## Rules
- Never condescend or use a patronizing tone
- Never compare one student's work to another's
- Never reference the student by name or any identifying
  information
- Focus on the writing and analysis, not the student as a person
- Use "the memo" or "the brief" not "your memo" where possible
  to depersonalize criticism
- When noting errors, explain the correct approach rather than
  just marking something wrong
```

Load this voice file into a project folder dedicated to feedback for a particular course. Every feedback conversation will inherit this tone.

### Step 2: Build a rubric

If you do not already have a rubric, ask the AI to help you build one. A clear rubric makes AI feedback more precise and makes human review of that feedback faster.

```text
I am providing feedback on legal memoranda in my 1L Legal Research
and Writing course. The assignment asks students to analyze whether
a client has a viable negligence claim based on a fact pattern
I provided.

Build a feedback rubric with the following dimensions:

1. Issue identification — did the student identify all relevant
   legal issues?
2. Rule statement — is each legal rule stated completely and
   accurately?
3. Application — does the student apply the rule to the specific
   facts (not just restate the rule or the facts)?
4. Counterargument — does the student address the strongest
   opposing position?
5. Organization — does the memo follow a logical structure
   with clear transitions?
6. Writing quality — is the prose clear, concise, and
   professional?
7. Citation — are legal authorities cited correctly and
   appropriately?

For each dimension, define what "strong," "competent," "developing,"
and "insufficient" performance looks like. Use specific, observable
criteria — not subjective impressions.
```

### Step 3: Generate feedback on a student's draft

Remove all identifying information from the student's work, then paste it into your feedback project folder.

```text
Using the rubric and voice file for this project, provide detailed
feedback on the following legal memorandum draft. The assignment
was [brief description of the assignment].

[Paste the de-identified student draft]

For each rubric dimension:
1. Rate the performance (strong / competent / developing /
   insufficient)
2. Quote a specific passage that illustrates the rating
3. Explain what the student did well and what needs improvement
4. Suggest one specific revision the student could make

After the dimension-by-dimension analysis, provide:
- An overall assessment (2-3 sentences)
- The three most important things the student should focus on
  in revision, in priority order
- One thing the student should keep doing because it is working
```

### Step 4: Review and personalize

This is the essential step. Read the AI's feedback with your instructor's eye and make adjustments:

- **Accuracy:** Does the AI's evaluation match your own reading? Sometimes the AI will praise analysis that you find superficial, or criticize a creative approach that is actually strong.
- **Calibration:** Is the feedback appropriately calibrated for this student's level? A 1L in Week 3 needs different feedback than a 3L in a seminar.
- **Tone:** Does the feedback strike the right balance of encouragement and criticism for this student?
- **Priority:** The AI may identify ten issues. A student can realistically address two or three. Prioritize.
- **Personal touch:** Add a sentence or two that only you can write — a reference to something the student said in class, encouragement about their progress, or a connection to a concept you discussed.

The AI generates the scaffold. You make it human.

### Step 5: Identify patterns across submissions

After providing feedback on several submissions, AI can help you identify common issues across the class. This is useful for planning review sessions, adjusting instruction, and creating targeted supplementary materials.

```text
I have now reviewed 15 student memoranda using our rubric. Here are
the dimension ratings for each:

[Paste a summary: e.g., "Student A: Issue ID - strong, Rule -
competent, Application - developing..." — no names or IDs]

Analyze the patterns:
1. Which rubric dimensions show the most widespread weakness?
2. Are there common errors that appear in multiple submissions?
3. Based on these patterns, what should I prioritize in my
   next class session?
4. Suggest a 15-minute in-class exercise that addresses the
   most common weakness
```

---

## Privacy and FERPA Considerations

!!! danger "Protect student data — check your tools"
    Student education records are classified as **Level 3 (Restricted)** under [Vanderbilt's Data Classification Guidelines](https://www.vanderbilt.edu/cybersecurity/guidelines/data-classification/) due to FERPA protections. Before using any AI tool with student data, verify that the tool meets your institution's requirements for restricted data.

    1. **Remove identifying information** before pasting student work into free or public AI tools. This includes student names, student ID numbers, institutional email addresses, course section numbers (if small enough to be identifying), and any personal details the student included in their writing.

    2. **Check your tools against your institution's data classification.** Free and public AI tools (ChatGPT free tier, Claude.ai free tier) are not appropriate for student records. Enterprise or institutional AI tools may be approved — check with your IT security office. Local tools (Excel, R, Claude Code running locally) do not transmit data to third-party servers.

    3. **Do not use AI to make final grading decisions.** AI-generated feedback is a drafting aid, not a grading authority. The grade is your professional judgment.

    4. **Check your institution's policies.** Some institutions have specific policies on AI use with student data. Follow them even if they are more restrictive than the guidance here.

    5. **Be transparent.** If you use AI as part of your feedback process, consider disclosing that to students. Norms are evolving, and transparency builds trust. A simple syllabus note suffices: "I use AI tools as a drafting aid when preparing feedback on student writing. All feedback is reviewed and finalized by me before being returned to you."

**Why this matters beyond compliance:** Even if your institution's policies do not explicitly address AI, FERPA protects education records — which includes student work and grades. Uploading identifiable student work to a public AI platform creates risks that are easy to avoid by removing identifying information or using institutionally approved tools.

---

## When AI Feedback Is Appropriate vs. When Personal Feedback Is Essential

AI-assisted feedback works well for:

- **Structural analysis** — evaluating IRAC compliance, organization, and completeness
- **Writing mechanics** — identifying citation errors, unclear sentences, passive voice overuse
- **Rubric-based evaluation** — rating performance on defined dimensions
- **First-draft feedback** — giving students detailed comments on early drafts when they have time to revise
- **Large-enrollment courses** — where the alternative is minimal feedback, not detailed personal comments

Personal feedback is essential for:

- **Students who are struggling** — they need to hear from you, not from a generated analysis
- **Final evaluative feedback** — end-of-semester assessments that carry significant weight
- **Encouragement and motivation** — a sentence from their professor means more than a paragraph from an AI
- **Sensitive situations** — when the writing reveals personal struggles, confusion, or academic integrity concerns
- **Office hours follow-up** — when a student comes to discuss feedback, you need to have actually read and engaged with their work

The general principle: AI can handle breadth (giving detailed feedback to every student on every draft). Humans should handle depth (the moments where individual attention matters most). The combination — AI-generated structural feedback plus human-added personal comments — gives students more and better feedback than either approach alone.

---

## Example: Reviewing a Legal Memorandum

Here is a realistic example of how the workflow looks in practice. Suppose a 1L student has submitted a legal memorandum analyzing whether a restaurant is liable for a customer's slip-and-fall injury.

**Your prompt (with de-identified student work):**

```text
Using our feedback rubric and voice file, review this 1L legal
memorandum. The assignment asked students to analyze whether
Riverside Grill is liable for negligence when a customer slipped
on a wet floor near the salad bar. The fact pattern includes a
"wet floor" sign that was partially obscured by a display stand.

[Paste de-identified memo — approximately 5-8 pages]

Provide rubric-based feedback. Pay particular attention to:
- Whether the student properly distinguishes between the duty
  of care owed to invitees vs. licensees
- Whether the application section uses specific facts from the
  fact pattern or relies on conclusory statements
- Whether the counterargument section addresses the comparative
  fault issue
```

**What you do with the AI's output:** Read it. Mark the two or three most important points. Add a personal note — perhaps the student nailed the duty analysis and you want to acknowledge that, or perhaps the student is making the same organizational mistake they made on the last assignment and you want to explicitly connect the feedback. Then return the combined feedback to the student.

---

## Limitations

**AI does not grade.** It can evaluate against rubric criteria, but the final assessment of quality — the grade — is a professional judgment that belongs to you. AI can inform that judgment; it should not make it.

**Tone calibration is imperfect.** The AI may be too harsh for a struggling student or too gentle for a student who needs a push. Always review tone in context.

**AI may miss creative analysis.** A student who takes an unconventional but valid approach may be marked down by an AI evaluating against a standard rubric. Watch for this and override when appropriate.

**Feedback fatigue applies to AI output too.** If every student gets three pages of generated feedback, the volume can be overwhelming. Prioritize ruthlessly — highlight the two or three most important points and let the rest go.

---

## Next Steps

<div class="grid cards" markdown>

-   **Build your feedback voice**

    ---

    The voice file technique ensures consistent, appropriate tone across all your feedback.

    [:octicons-arrow-right-24: Teaching AI Your Voice](../essentials/voice.md)

-   **Design your rubrics first**

    ---

    Rubric-based feedback is only as good as the rubric. Design exams and rubrics before the feedback stage.

    [:octicons-arrow-right-24: Exam Drafting & Rubrics](exam-drafting.md)

-   **Set up a project folder**

    ---

    A feedback project folder stores your rubric, voice file, and feedback conventions across the semester.

    [:octicons-arrow-right-24: AI Project Folders](../essentials/project-folders.md)

</div>
