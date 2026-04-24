# Exam Drafting & Rubrics

**Using AI to draft exam questions, build scoring rubrics, create model answers, and stress-test difficulty — while maintaining academic integrity and protecting student privacy.**

Exam writing is a peculiar skill. We need questions that are challenging but fair, that test what we actually taught, that distinguish among student ability levels, and that can be graded consistently. We also need rubrics that make grading efficient and defensible, and model answers that help teaching assistants grade reliably. AI can help with all of this — as a drafting partner, a difficulty-calibration tool, and a rubric-generation engine.

!!! warning "Two important practices"
    **1. Rework AI-generated questions before using them.** Students have access to the same AI tools. If you paste an AI-generated question directly into an exam, a student could paste it back into ChatGPT and get a detailed analysis. Modify, combine, or substantially rework AI-generated questions before they appear on an exam. **2. Know your data classification before inputting student information.** Free and public AI tools (ChatGPT, Claude.ai free tier) are not appropriate for student records. Before using any AI tool with student data, check your institution's data classification guidelines (for example, [Vanderbilt's Data Classification Guidelines](https://www.vanderbilt.edu/cybersecurity/guidelines/data-classification/)). Student education records are typically classified as restricted under FERPA. See the [privacy section below](#privacy-and-academic-integrity) for specifics.

---

## Why This Matters

Exam drafting is time-consuming and high-stakes. A poorly worded question can confuse students, invite unintended answers, or fail to test what you intended. A vague rubric makes grading inconsistent and difficult to defend when students challenge grades. A model answer that misses key issues creates problems for TAs.

AI helps by generating first drafts quickly, letting you spend your time on refinement rather than blank-page creation. It is also a useful reviewer — you can ask it to evaluate your questions from a student perspective, identify ambiguities you did not notice, and check whether your rubric covers the range of reasonable answers.

---

## The Workflow

### Step 1: Draft exam questions

Start by telling the AI what the exam should cover, the format, and the difficulty level. Be specific about the type of analysis you expect.

**Essay question prompt:**

```text
I teach a 4-credit Constitutional Law I course for first-year law
students. I am drafting the final exam — a 3-hour, open-book exam
with two essay questions.

Question 1 should be a fact pattern testing the following doctrinal
areas:
- Fourteenth Amendment substantive due process
- Rational basis review vs. intermediate scrutiny
- The interplay between equal protection and due process claims

The fact pattern should:
- Involve a state regulation (not federal) — make it a plausible
  but fictional statute
- Present facts that make the level of scrutiny genuinely arguable
  (not obvious which standard applies)
- Include at least one red herring that a weaker student might
  spend time on but a stronger student will recognize as
  irrelevant or secondary
- Be answerable in approximately 90 minutes by a well-prepared 1L

Draft the question. After the fact pattern, include 2-3 specific
sub-questions that direct the student's analysis.
```

**Multiple choice prompt:**

```text
Draft 10 multiple choice questions for a midterm in my Evidence
course. The questions should test:
- Relevance (FRE 401-403): 3 questions
- Hearsay rule and exceptions (FRE 801-807): 4 questions
- Character evidence (FRE 404-405): 3 questions

For each question:
- Write a short fact pattern (2-3 sentences) followed by a
  question stem and four answer choices
- Make exactly one answer clearly correct
- Make the remaining three plausible but wrong — each wrong answer
  should reflect a common student misconception, not an obviously
  absurd choice
- After each question, include a brief explanation of why the
  correct answer is correct and why each distractor is wrong

Target difficulty: a well-prepared 2L should get 7-8 out of 10
correct. The hardest 2-3 questions should require applying
rules to novel fact patterns, not just recalling definitions.
```

**Practical exercise prompt:**

```text
Draft a practical exercise for my Legal Writing II class. The
exercise should simulate a real-world task:

A partner at a mid-size firm has asked the student (a junior
associate) to review a client's situation and write a short
memorandum (3-5 pages) analyzing whether the client has a viable
claim.

The fact pattern should involve [area of law] and should:
- Include some facts that favor the client and some that do not
- Require the student to identify the relevant legal standard
  without being told what it is
- Include one factual ambiguity that the student should flag
  and discuss (not ignore)
- Be completable in a 2-hour take-home window

Draft the partner's email to the associate (this is what students
see) and the underlying client intake notes.
```

### Step 2: Stress-test difficulty

This is one of the most valuable uses of AI in exam design. After drafting a question, ask the AI to evaluate it from a student's perspective.

```text
Here is the essay question I drafted for my Con Law final:

[Paste your question]

Evaluate this question as if you were a strong 2L student (top
quarter of the class). Specifically:

1. Can you identify all the issues the question is testing? List
   them. If a well-prepared student might miss an issue, flag it.
2. Is the question answerable in 90 minutes? Walk through a
   realistic time allocation for each sub-question.
3. Are any parts ambiguous in ways I did not intend? Point out
   any language that could be read two ways.
4. Is the red herring effective? Would a strong student recognize
   it, or is it too obvious / too subtle?
5. Does the question actually test the doctrinal areas I intended,
   or does it inadvertently test something else?
6. Could a student answer this well without having taken my course
   (e.g., using only general legal reasoning)? If so, the question
   is not testing course-specific knowledge effectively.
```

This prompt often reveals problems: a question that looks like it takes 90 minutes actually requires two hours when you account for reading time and outlining, or a "tricky" issue is actually obvious, or the fact pattern inadvertently raises an issue you did not intend to test.

### Step 3: Build the rubric

A good rubric makes grading faster, more consistent, and more defensible. Ask the AI to draft one based on your exam question.

```text
Using the essay question above, create a grading rubric with the
following structure:

For each major issue the question tests:
1. Issue identification (did the student spot it?) — [points]
2. Rule statement (did they state the correct legal standard?) — [points]
3. Analysis (did they apply the rule to the facts with specificity?) — [points]
4. Counterargument (did they address the strongest opposing position?) — [points]

Total points should sum to 100. Weight the issues according to their
relative importance and difficulty.

For each issue, describe:
- What an excellent answer (A range) looks like
- What a competent answer (B range) looks like
- What a passing answer (C range) looks like
- What a failing answer looks like

Also include:
- 5 points for organization and writing quality
- A note on how to handle answers that raise valid issues I did
  not anticipate
```

### Step 4: Create model answers

Model answers serve two purposes: they help TAs grade consistently, and they can be shared with students after the exam as a learning tool.

```text
Write a model answer for the essay question above. The answer should:

1. Represent an A-quality response — thorough, well-organized,
   and analytically rigorous
2. Follow IRAC/CREAC structure for each major issue
3. Address counterarguments where reasonable students could
   disagree
4. Be the length a strong student could realistically produce
   in 90 minutes (approximately 1500-2000 words, not a treatise)
5. Include marginal annotations explaining why each section earns
   full credit under the rubric

After the model answer, write a brief "common mistakes" section
listing the 5-6 errors you expect to see most frequently.
```

!!! tip "Multiple model answers"
    For questions where reasonable students could reach different conclusions, ask the AI to generate two model answers reaching opposite results. This helps TAs avoid penalizing students who take a defensible position that differs from the "expected" answer.

### Step 5: Iterate and finalize

Review everything the AI produced. Modify the questions so they are not easily reproduced by a student using the same AI tool. Adjust the rubric based on your assessment of what the question actually tests. Edit the model answer to reflect how you would approach the problem.

---

## AI as Exam Reviewer

Beyond drafting, AI is useful as a reviewer of exams you have already written. Paste in a question you drafted yourself and ask:

```text
I wrote this exam question for my [course] final. Review it for:

1. Clarity — is every sentence unambiguous?
2. Fairness — does it test what I taught, or does it require
   outside knowledge?
3. Discrimination — will it effectively distinguish between
   students who understand the material and students who do not?
4. Completeness — does my rubric cover every reasonable way
   a student might approach this question?
5. Timing — is this answerable in the time allotted?

Be candid. If this is a bad question, tell me why and suggest
how to fix it.
```

---

## Privacy and Academic Integrity

!!! danger "Protect student data — check your tools"
    Student education records are protected under FERPA and are typically classified as restricted by university data governance policies (for example, [Vanderbilt's Data Classification Guidelines](https://www.vanderbilt.edu/cybersecurity/guidelines/data-classification/)). Before using any AI tool with student data, check your institution's specific requirements.

    **What this means in practice:**

    - **Free and public AI tools** (ChatGPT free tier, Claude.ai free tier, Gemini) are **not appropriate** for student records. These platforms may retain conversation data and are not VUIT-managed.
    - **Enterprise or institutional AI tools** may be approved for some uses — check with your institution's IT security office.
    - **Local tools** (Excel, R, Python, Claude Code running locally) do not transmit data to third-party servers and are generally safer for sensitive data.

    When in doubt, **remove all identifying information** (names, student IDs, grades, section numbers) before using any AI tool. This applies to rosters, grade spreadsheets, individual performance data, and identifying details in exam answers.

**On exam security:** AI-generated exam questions are not inherently insecure, but they are reproducible. If you paste a fact pattern into ChatGPT and ask it to write a Con Law exam question, a student could paste your exam question back into ChatGPT and get a detailed analysis. The defense is simple: never use AI-generated questions without substantial modification. Change the facts, combine elements from multiple generated questions, add your own twists, and rework the phrasing.

**On disclosure:** If your institution has a policy on AI use in course materials, follow it. Even without a formal policy, consider noting in your syllabus that AI tools were used as a drafting aid in course development. Transparency builds trust.

---

## Practical Tips

!!! tip "Year-over-year exam development"
    Keep your course project folder active across semesters. After each exam, add a note about what worked and what did not — which questions discriminated well, which rubric elements were unclear, which model answer sections needed revision. Over time, the project folder becomes an institutional memory for your exam design process.

!!! tip "AI for exam accommodation"
    If you need to create modified exam formats for students with accommodations (extended time, alternative formats), AI can help you adapt an existing exam. For example: "Reformat this 3-hour essay exam into a 4.5-hour version with the same content. Add a short-answer warm-up section (15 minutes) before each essay to help students with processing accommodations organize their thinking." Note: do not input the student's name or specific accommodation details into the AI.

---

## Limitations

**AI-generated questions may be too clean.** Real exam questions often have productive ambiguity — facts that are deliberately unclear, issues that are genuinely close calls. AI tends to create questions with clear right answers. You may need to introduce ambiguity deliberately.

**Rubrics may not anticipate creative answers.** The AI builds rubrics based on expected analytical paths. Students sometimes take creative approaches that are valid but unpredicted. Always include a rubric provision for "raises valid issues not anticipated by the model answer."

**Model answers may be too thorough.** AI-generated model answers often read like a professor's treatise, not like what a student could write under exam conditions. Insist on realistic length and complexity constraints.

---

## Next Steps

<div class="grid cards" markdown>

-   **Design the course first**

    ---

    Exam questions should flow from learning objectives. Design the syllabus before the exam.

    [:octicons-arrow-right-24: Syllabus & Course Design](syllabus-design.md)

-   **Give feedback on student work**

    ---

    After the exam, AI can help you provide structured feedback at scale.

    [:octicons-arrow-right-24: Student Feedback](student-feedback.md)

-   **Stress-test your exam**

    ---

    Use the plan review technique to identify problems before exam day.

    [:octicons-arrow-right-24: Stress-Test Any Plan](../workflows/plan-review-browser.md)

</div>
