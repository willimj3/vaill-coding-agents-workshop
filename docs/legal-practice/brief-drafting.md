# Brief Drafting

<span class="badge-teal">Works in chatbots and Claude Code</span>

Legal writing is one of the most demanding forms of professional writing. It requires precision, structure, citation to authority, and persuasive framing -- all within tight deadlines. AI can help with parts of this process, but the integration requires care.

This page covers how to incorporate AI into your brief-writing workflow, where it genuinely accelerates the process, and where it creates serious risks if you are not vigilant.

!!! danger "The most important thing on this page"

    **AI will fabricate case citations.** This is not a bug that will be fixed in the next model. It is a fundamental characteristic of how large language models work. Every citation AI produces must be verified in Westlaw, Lexis, or another authoritative source. Attorneys have been sanctioned for submitting AI-generated briefs with fabricated citations. Do not let this happen to you.

---

## Where AI Helps in Brief Writing

AI is genuinely useful at specific stages of the brief-writing process:

| Stage | AI Contribution | Human Contribution |
|-------|----------------|-------------------|
| **Research** | Generate leads, summarize cases you provide, identify arguments | Verify every source, evaluate relevance, assess precedential weight |
| **Outlining** | Propose argument structure, suggest counterarguments | Choose strategy, determine emphasis, decide what to include/exclude |
| **Drafting** | Produce first-draft sections, especially factual background | Rewrite for voice, precision, and persuasive impact |
| **Cite-checking** | Identify where citations are needed, format citations | Verify every citation exists and says what you claim it says |
| **Editing** | Identify inconsistencies, tighten prose, check for logical gaps | Final judgment on tone, strategy, and persuasive choices |

Notice the pattern: AI does the mechanical work. You do the judgment work. The workflow is delegation, not abdication.

---

## The Brief-Writing Workflow

Here is a five-stage workflow that integrates AI effectively. You do not need to follow it rigidly, but the sequence matters: research before outlining, outlining before drafting, and cite-checking before filing.

### Stage 1: Research and Issue Framing

Start by doing your own research -- or at least your own thinking about the issues. Then use AI to expand your research, not replace it.

```text
I am drafting a motion to dismiss in [jurisdiction] state court. The
plaintiff alleges [cause of action] based on the following facts:
[brief summary].

Our primary arguments are:
1. [First argument]
2. [Second argument]
3. [Third argument]

For each argument:
- Explain the legal standard
- Identify the key elements the plaintiff must establish
- Suggest the strongest counterarguments the plaintiff will raise
- Recommend how to frame our argument to address those counterarguments

Do NOT cite specific cases. I will do my own case research. Focus on
argument structure and legal reasoning.
```

!!! tip "Why we say 'do NOT cite specific cases'"

    Telling AI not to cite cases avoids the hallucination problem entirely at this stage. You get the argument structure -- which AI handles well -- without the fabricated citations. You then do the case research yourself in Westlaw or Lexis, where you know the citations are real.

### Stage 2: Outline with IRAC Structure

Once you have your argument framework, use AI to build a detailed outline. IRAC (Issue, Rule, Application, Conclusion) is the structural backbone of legal writing, and AI follows it well when you ask explicitly.

```text
Create a detailed outline for a motion to dismiss brief using IRAC
structure. The brief should be approximately [X] pages.

For each argument:
- ISSUE: State the legal question in one sentence
- RULE: Describe the legal standard (I will add citations later)
- APPLICATION: Show how the facts apply to the rule. Be specific
  about which facts support our position and which facts the
  plaintiff will emphasize.
- CONCLUSION: State the result we seek for this argument

Arguments to include:
1. [First argument with key facts]
2. [Second argument with key facts]
3. [Third argument with key facts]

Also include sections for:
- Statement of Facts (chronological, citing to the record)
- Procedural History
- Standard of Review
- Conclusion and Prayer for Relief

For the Statement of Facts, organize by [chronological / topical]
and flag which facts are most important to our arguments.
```

### Stage 3: Draft Sections

Now you can have AI draft individual sections. Draft them one at a time, not all at once. This lets you review and redirect between sections.

```text
Using the outline above, draft the [SECTION NAME] section.

Guidelines:
- Write in formal legal prose appropriate for a [court level] brief
- Use topic sentences that state the legal point of each paragraph
- Keep paragraphs to 3-5 sentences
- Leave placeholders like [CITATION NEEDED] where case citations
  should go -- do not invent citations
- Use the facts from the record as stated in our outline
- Write persuasively but accurately -- do not overstate the facts
  or the law
- Target approximately [X] words for this section
```

The key instruction is `Leave placeholders like [CITATION NEEDED]`. This forces the AI to flag where authority is needed without fabricating it. You then fill in the citations from your own research.

### Stage 4: Cite-Check and Verify

This is the stage where you do the most work -- and where cutting corners creates the most risk.

For every `[CITATION NEEDED]` placeholder:

1. Find a real case that supports the proposition
2. Read the case (at least the relevant section) to confirm it says what you need it to say
3. Verify the case has not been overruled or distinguished in your jurisdiction
4. Insert the proper citation in correct Bluebook or local format

!!! danger "Do not skip this step"

    In 2023, an attorney was sanctioned by a federal court for submitting a brief with six fabricated case citations generated by ChatGPT. The cases did not exist. This is not a cautionary tale from the early days of AI -- it is an ongoing risk with every current model. If you use AI for brief drafting and do not verify every citation, you are one filing away from a sanctions motion.

For sections the AI drafted with text (not just citations), also verify:

- [ ] The legal standards stated are accurate for your jurisdiction
- [ ] The characterization of facts matches the record
- [ ] No factual assertions are made that are not supported by the record
- [ ] The logical structure of each argument is sound
- [ ] No inadvertent admissions or concessions are buried in the draft

### Stage 5: Revise for Voice and Persuasion

AI prose is competent but generic. After verification, revise the draft for:

- **Your voice.** Load a [voice file](../essentials/voice.md) for legal writing, or edit manually.
- **Persuasive framing.** AI tends toward neutral exposition. Advocacy requires emphasis, strategic word choice, and deliberate paragraph ordering.
- **Concision.** AI drafts are often 20-30% too long. Cut aggressively.
- **Flow.** Check transitions between sections and arguments. AI handles individual sections better than it handles the connections between them.

---

## A Voice File for Legal Writing

If you use AI regularly for brief drafting, create a voice file specific to legal writing. Here is a starting point:

```markdown
# Legal Writing Voice

## Tone
- Formal but not stiff. Write for a busy judge, not a law review.
- Direct. Lead with your strongest point, not background.
- Confident without being aggressive. "The complaint fails to state
  a claim" not "the complaint clearly and obviously fails."

## Structure Rules
- Topic sentences carry the legal argument. A reader who only reads
  topic sentences should understand the argument.
- One idea per paragraph. If you need a transition, use a new paragraph.
- Short sentences for legal standards. Longer sentences (with care)
  for factual application.
- Maximum 25 words per sentence as a default. Break this rule only
  when parallel structure or a complex factual recitation requires it.

## Citation Practice
- Cite after the legal proposition, not before it.
- Pin cite to the specific page. Never cite to the first page only.
- Parenthetical explanations for cases that are not self-evident.
- String cites only when the number of authorities is the point.

## Vocabulary
- "The Court" not "the court" when referring to the tribunal you
  are addressing.
- "Plaintiff" and "Defendant" on first use; parties' names thereafter
  if it improves readability.
- Avoid: "clearly," "obviously," "it is well-established that" (show,
  don't tell).
- Ban list: "delve," "navigate," "robust," "nuanced," "multifaceted"
  (AI defaults, not legal writing).

## What I Will Always Write Myself
- The opening paragraph of any brief
- The conclusion and prayer for relief
- Any section involving judicial discretion arguments
- Strategic framing of key facts
```

---

## Prompt Engineering for Legal Arguments

Legal arguments have a specific structure, and prompts that reflect that structure produce better results. Here are patterns that work:

### For Statutory Interpretation Arguments

```text
Draft an argument that [statute section] should be interpreted to
[our position].

Structure as:
1. Plain language of the statute (quote the relevant text)
2. Statutory context (how this section fits within the broader statute)
3. Legislative history (if available and helpful -- note if you are
   uncertain about legislative history)
4. Policy considerations supporting our interpretation
5. Distinguish the opposing interpretation and explain why it fails

Use [CITATION NEEDED] placeholders throughout. Do not invent citations.
```

### For Factual Sufficiency Arguments

```text
Draft an argument that the plaintiff's [specific claim] fails because
the complaint does not adequately allege [missing element].

Facts as alleged in the complaint:
[Paste relevant factual allegations]

Structure as:
1. State the elements of the claim
2. Identify which element is insufficiently pled
3. Explain what specific factual allegations would be necessary
4. Show that the complaint's allegations fall short
5. Address the most likely counterargument (that the allegations
   are sufficient because [anticipated argument])

Write for a [Twombly/Iqbal / state-specific] plausibility standard.
Use [CITATION NEEDED] placeholders.
```

---

## When to Write From Scratch Instead

AI is not always the right tool. Write from scratch when:

- **The argument is novel.** If you are making a first-impression argument, AI has nothing to pattern-match against. Your reasoning will be stronger.
- **The facts are the argument.** Some briefs turn on how you tell the story. AI does not know your client, your strategy, or which facts to emphasize.
- **The brief is short.** For a two-page letter brief or a concise motion, writing from scratch is often faster than prompting, reviewing, and revising AI output.
- **Voice matters more than coverage.** Opening statements, closing arguments, and any filing where persuasion depends on rhetorical skill rather than comprehensive analysis.
- **You are learning the area.** Writing a brief from scratch teaches you the law in a way that editing AI output does not. If you are new to an area, do the writing yourself.

---

## Practical Tips for Integration

**Start with the section you know least about.** Use AI to draft the section where you need the most help, then write the sections you know well yourself. This plays to AI's strength (broad coverage) while preserving your strength (deep expertise in your core areas).

**Review in print.** Print the AI draft and read it on paper. You will catch errors and awkward phrasing on paper that you miss on screen. This is true for all legal writing, but especially true for AI-assisted drafts.

**Keep a "lessons learned" note.** After each brief, note what the AI did well and where it fell short. Over time, this becomes your guide for which sections to delegate and which to write yourself.

**Use version control.** Save the AI's draft separately from your revised version. If you need to trace where a particular phrase or argument came from, you want a clear record.

**Budget time for verification.** AI drafting saves time on the initial draft but adds time for verification. Plan accordingly. A realistic time budget: 30% savings on drafting, 20% added for verification, net 10% time savings -- plus a better first draft to work from.

---

## Ethics Considerations for AI-Assisted Brief Drafting

!!! danger "Duty of Candor (Model Rule 3.3)"

    Submitting a brief with fabricated citations violates the duty of candor to the tribunal. This is not a gray area. Every citation in your brief must be to a real authority that says what you claim it says. The fact that an AI generated the citation is not a defense -- it is an aggravating factor, because it suggests you did not verify your own work product.

**Competence and diligence.** Using AI for brief drafting is permissible, but the duty of competence requires that you understand how AI generates text and why it fabricates citations. You must build verification into your workflow, not treat it as optional.

**Disclosure.** Some courts have adopted local rules requiring disclosure of AI use in legal filings. Check your jurisdiction's rules. Even where disclosure is not required, consider whether transparency with the court serves your client's interests.

**Work product.** AI-generated drafts may raise questions about work product protection if the opposing party seeks discovery about your drafting process. Consider how you would respond to a discovery request about AI use in preparing the brief.

**Client communication.** Be transparent with your clients about your use of AI tools. Many clients will welcome the efficiency gains; some may have concerns. Address this proactively in your engagement letter or a separate communication.

---

## Next Steps

<div class="grid cards" markdown>

-   **Build your legal writing voice file**

    ---

    Adapt the template above with your own writing samples. Load it into a Claude.ai Project or your CLAUDE.md.

    [:octicons-arrow-right-24: Teaching AI Your Voice](../essentials/voice.md)

-   **Set up cite-checking habits**

    ---

    Before you use AI for any brief, establish a verification workflow. Decide where you will check every citation and how you will document that you did.

-   **Try the workflow on a low-stakes filing**

    ---

    Start with a routine motion or response -- not your biggest case. Learn the rhythm of the five-stage workflow before applying it to high-stakes work.

</div>

---

## Related Pages

- [Legal Research](legal-research.md) -- AI-assisted research to feed your brief-writing workflow
- [Contract Review](contract-review.md) -- Similar AI review techniques applied to contracts
- [Prompt Engineering](../essentials/prompting.md) -- The general prompt engineering framework
