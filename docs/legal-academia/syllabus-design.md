# Syllabus & Course Design

**Using AI to draft syllabi, build reading lists, map learning objectives, and create course materials — with an AI project folder for each course you teach.**

Designing a new course is one of the most intellectually demanding things law faculty do. It requires synthesizing a field into a coherent arc, choosing readings that build on each other, writing learning objectives that are both ambitious and measurable, and producing materials that work for students at a specific level. It is also one of the tasks where AI assistance is most immediately useful — not because AI understands pedagogy better than we do, but because it is very good at the structural work: organizing, sequencing, mapping dependencies, and generating options we can evaluate.

!!! tip "The approach on this page"
    We treat AI as a course design partner, not a course designer. It generates drafts, suggests readings, proposes sequences, and maps objectives to assessments. We make all the substantive decisions — what to include, what to cut, what the course is really about. The AI handles the scaffolding; we provide the pedagogical judgment.

---

## Why This Matters

Every law professor has experienced the blank-page problem: you have been asked to teach a new seminar, or you want to redesign an existing course, and the sheer number of decisions to make is paralyzing. What readings should you include? In what order? How do you balance breadth and depth? What are the learning objectives? How do assessments connect to those objectives?

AI does not resolve these questions — they require your expertise and pedagogical instincts. But it can:

- Generate a first-draft syllabus that you revise rather than creating from scratch
- Suggest readings you might not have considered, especially from adjacent fields
- Map your learning objectives to specific class sessions and assessments
- Produce discussion questions and hypotheticals for each week
- Adapt materials for different student levels (1L survey vs. 3L seminar)
- Identify gaps in your course design — topics your objectives claim to cover but your readings do not address

The result is not a finished syllabus. It is a structured draft that gives you something to react to, critique, and reshape — which is faster and often better than starting from nothing.

---

## The Workflow

### Step 1: Set up a course project folder

Create a project in ChatGPT or Claude.ai for each course you teach. The project instructions capture your stable preferences — your pedagogical approach, your institution's requirements, your assessment philosophy. Per-semester details (meeting times, specific students) go into individual conversations, not the project file.

```text
# Course Design: [Course Name]

## About me
I am a [title] at [institution] teaching [area of law]. I have
taught this subject [number] times / This is a new course for me.

## Course parameters
- Level: [1L required / upper-level elective / seminar / LL.M.]
- Students: [typical enrollment size and background]
- Credits: [number]
- Meeting pattern: [e.g., 2x per week, 75 minutes per session]
- Semester length: [number of weeks of instruction]

## My pedagogical approach
- [Describe how you teach — Socratic method, problem-based,
  discussion-heavy, lecture with exercises, etc.]
- [Any specific commitments — e.g., "I always include at least
  one skills-based exercise per unit"]
- [Assessment philosophy — e.g., "I use a mix of a final exam
  and shorter writing assignments"]

## Standing instructions
- When suggesting readings, include both canonical texts and
  recent scholarship (last 3-5 years)
- Always suggest more readings than I need so I can choose
- Organize suggestions by difficulty level when the course
  includes students with varied backgrounds
- For each reading, estimate the time a student would need
  to complete it
- When drafting learning objectives, use Bloom's taxonomy
  verbs and make each objective measurable
```

### Step 2: Generate a course outline

With your project folder loaded, start the design conversation. Be specific about what you want the course to accomplish.

```text
I am designing a new seminar: "Artificial Intelligence and the Law."
This is a 3-credit upper-level seminar for 2Ls and 3Ls, meeting
twice per week for 14 weeks. Maximum enrollment is 16 students.

Prerequisites: Constitutional Law I, at least one of Administrative
Law or Legislation & Regulation.

The seminar should cover:
- Foundational concepts in AI and machine learning (enough for
  legal analysis, not a CS course)
- Algorithmic decision-making in government (criminal justice,
  benefits, immigration)
- AI and intellectual property (copyright, patent, trade secrets)
- AI regulation (existing frameworks, proposed legislation,
  comparative approaches)
- Liability frameworks for AI-caused harm
- AI and the legal profession (ethics, practice, access to justice)

Learning outcomes — by the end of this course, students should be
able to:
1. Explain how major AI systems work at a level sufficient to
   analyze their legal implications
2. Identify and analyze constitutional and statutory issues
   raised by algorithmic decision-making
3. Evaluate proposed regulatory frameworks for AI using multiple
   analytical lenses
4. Draft a research paper that makes an original contribution
   to the AI and law literature

Generate a week-by-week syllabus with:
- Topic for each session
- 2-3 suggested readings per session (with estimated page counts)
- One discussion question per session
- How each week maps to the learning outcomes above

Also suggest an assessment structure that supports the learning
outcomes.
```

This prompt is long, but that is appropriate for a complex task. The more specific you are about what you want, the more useful the output will be.

### Step 3: Refine the reading list

The AI's initial reading suggestions will be a mix of good picks, outdated choices, and hallucinated sources. Review the list critically.

```text
For the reading list you suggested, I need you to:

1. For each reading, tell me how confident you are that this is a
   real, published work (high / medium / low)
2. Suggest alternatives for any reading you rated medium or low
   confidence
3. For weeks 3-5 (algorithmic decision-making in government),
   the readings are too theory-heavy. Suggest readings that
   include concrete case studies or real-world examples
4. I want to include at least one reading per unit from a scholar
   who is not a white man. Identify where my current list lacks
   diversity and suggest additions
5. Flag any readings that are more than 40 pages — that is too
   much for a single session combined with other assignments
```

!!! warning "Verify every reading"
    Just as with literature reviews, AI will suggest readings that do not exist. Before finalizing your syllabus, confirm every reading in your library catalog or legal databases. This is essential — you do not want students searching for an article that was never written.

### Step 4: Map learning objectives to assessments

One of the most useful things AI can do for course design is ensure alignment between what you say students will learn and how you assess whether they learned it.

```text
Here are my four learning outcomes and my proposed assessment structure
(a 30% midterm paper, a 50% final research paper, and 20% class
participation).

For each learning outcome, show me:
1. Which assessment(s) measure this outcome
2. Which class sessions specifically build toward this outcome
3. Whether any outcome is under-assessed or under-taught

If you find gaps — outcomes that are not adequately assessed or
sessions that do not clearly connect to any outcome — tell me
directly and suggest fixes.
```

### Step 5: Generate discussion questions and hypotheticals

This is a high-volume, low-stakes task where AI excels. You need dozens of discussion questions across a semester, and AI can generate them quickly. You curate and refine.

```text
For Week 6 (AI and Intellectual Property — Copyright), generate:

1. Five discussion questions ranging from foundational to advanced.
   The first two should be accessible to a student who did the
   readings but has not thought deeply about them. The last two
   should require synthesizing multiple readings or applying
   concepts to novel situations.

2. One hypothetical (2-3 paragraphs) that raises both a copyright
   issue and an adjacent issue (e.g., fair use and first amendment,
   or copyright and contract) that students must navigate together.
   Include enough facts that reasonable students could argue
   different sides.

3. One current-events connection — something that happened in the
   last two years that illustrates the week's themes. Include
   enough detail that I can use it as a class opener without
   additional research.
```

---

## Adapting for Different Student Levels

The same AI project folder can help you adapt materials for different audiences. This is particularly useful if you teach the same subject at multiple levels.

```text
I am adapting my AI and the Law seminar for two different audiences:

Audience A: 2L/3L JD students with a standard law school background
Audience B: LL.M. students, many of whom are trained in civil law
systems and have limited familiarity with U.S. constitutional law

For Week 4 (Due Process and Algorithmic Decision-Making):
1. What background readings would Audience B need that Audience A
   would not?
2. How should I modify the discussion questions to account for
   comparative perspectives?
3. Suggest one additional reading from a non-U.S. legal system
   that addresses the same issues from a different doctrinal
   framework
```

---

## Limitations

**Reading suggestions require verification.** AI may suggest articles that do not exist, books that are out of print, or cases that do not stand for what the AI claims. Verify every reading.

**AI does not know your students.** It cannot account for the specific dynamics of your classroom, the preparation level of students at your institution, or the pedagogical culture of your law school. Use AI suggestions as starting points, not final answers.

**Pedagogical judgment is yours.** AI can suggest a sequence, but it does not know that your students need a concrete case study in Week 2 to stay engaged, or that your institution requires coverage of a particular topic for bar preparation. Bring your teaching experience to every decision.

**Hallucinated current events.** When AI suggests "recent" examples, verify them. AI may describe events that did not happen or misstate the details of events that did.

---

## Practical Tips

!!! tip "AI for semester maintenance"
    Once your syllabus is set, the course project folder remains useful throughout the semester. Use it to:

    - Generate additional hypotheticals when a discussion falls flat
    - Create review materials before exams
    - Draft supplementary reading guides for complex topics
    - Adapt a lesson plan when a guest speaker cancels
    - Produce study guides that map readings to exam topics

!!! tip "Share your project folder structure, not your content"
    If a colleague is designing a similar course, share your project folder template (the instructions file from Step 1) rather than your specific readings and questions. The template is transferable; your specific choices reflect your expertise and your institution.

---

## Next Steps

<div class="grid cards" markdown>

-   **Build your course project folder**

    ---

    The project folder system that makes AI remember your preferences across conversations.

    [:octicons-arrow-right-24: AI Project Folders](../essentials/project-folders.md)

-   **Draft your exams**

    ---

    Use AI to create exam questions, rubrics, and model answers for the course you just designed.

    [:octicons-arrow-right-24: Exam Drafting & Rubrics](exam-drafting.md)

-   **Refine your voice**

    ---

    Ensure your syllabus and course materials sound like you, not like an AI.

    [:octicons-arrow-right-24: Teaching AI Your Voice](../essentials/voice.md)

</div>
