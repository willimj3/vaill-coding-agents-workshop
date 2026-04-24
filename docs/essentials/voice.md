# Teaching AI Your Voice

<span class="badge-gold">Works in chatbots and Claude Code</span>

AI has a house style. You have seen it -- the same cadence, the same filler words, the same way of saying nothing in three polished paragraphs. When you ask it to write for you, it writes like every other AI output. When you ask it to edit your work, it quietly overwrites your voice with its own.

The fix is not better prompting. It is giving the AI a reference document -- a "voice file" -- that captures how you actually write. Load it once, and every conversation starts with your patterns, not the AI's defaults.

---

## Before and After

Same request, same model. The only difference is whether a voice file was loaded.

=== "Without voice file"

    > The proposed regulatory framework represents a comprehensive approach to addressing the complex challenges inherent in emerging fintech oversight. Through a multifaceted analysis of existing regulatory structures and innovative compliance mechanisms, this memorandum aims to provide robust guidance for navigating the evolving landscape of digital financial services regulation.

=== "With voice file"

    > The CFPB's proposed rule fails on two fronts. First, it treats all digital payment platforms as equivalent -- ignoring that a peer-to-peer app serving unbanked consumers raises different risks than a corporate treasury tool. Second, the compliance timeline assumes fintechs can implement KYC protocols in 90 days. Industry data suggests 180 days minimum. We recommend the client submit comments challenging both provisions.

The first version could have been written by anyone -- or anything. The second sounds like a lawyer who knows the regulatory landscape and has a recommendation.

---

## Build Your Voice File

One path. Five steps. The most important step is step 4 -- examples teach the AI your patterns far more reliably than abstract rules. The most important non-step is loading the file into a persistent Project (step 5), not a one-off chat.

!!! tip "The Ban List -- do this first"
    These are the words AI uses that no human lawyer actually writes. If you add nothing else to your voice file, add this:

    *delve, leverage, multifaceted, furthermore, moreover, robust, compelling, navigate, foster, transformative, pivotal, it is important to note, it is worth mentioning, the landscape of*

    Every one is a diagnostic signal that the AI is ignoring your voice and reverting to its default. Ban them explicitly. Takes 30 seconds; gives immediate results.

**1. Start with your best writing.** Pull 5-10 pieces you are proud of -- a published article section, a brief that won, a client letter people praised, a memo where you nailed the analysis. Diversity of context matters more than volume. A brief and a client letter teach the AI more than five briefs. Paste all samples into a single chat window; do not worry about length.

**2. Let the AI analyze them, not you.** You are too close to your own voice to describe it accurately. Paste your samples plus this prompt into a fresh chat:

```text
Analyze these writing samples and extract my voice profile. For each
pattern you identify, cite the specific phrase or sentence that
demonstrates it. Cover:

1. How I open paragraphs -- what is the first sentence doing?
2. Sentence length patterns -- average, range, rhythm
3. Moves I repeat -- do I enumerate? Use parentheticals? Quantify?
4. Vocabulary I reach for vs. vocabulary I avoid
5. How I handle uncertainty, qualifications, and adverse authority
6. What I never do (identify any consistent absences)

Be specific. "Uses short sentences" is useless. "Lead sentences average
8 words; elaboration sentences average 18" is useful. Quote my text
as evidence for every claim.
```

This is the page's core deliverable. The prompt forces the AI to ground every observation in your actual text, not generic style advice. If the AI returns vague patterns ("you use transitions effectively"), your samples may be too short or too similar -- try adding a different genre.

**3. Ask it to build the voice spec.** From the analysis, use this prompt:

```text
Using the analysis above, write my voice spec. Format it as a style
guide that fits on a single page (300-500 words). Cover: tone and
stance, non-negotiable rules (numbered list, stated as constraints not
preferences), vocabulary to use vs. avoid, and how I handle evidence
and uncertainty. Every rule must be testable: instead of "write clearly,"
say "keep topic sentences under 12 words." Do not use adjectives where
a rule will do.
```

**4. Add annotated examples -- this is what matters most.** A rule that says "write short sentences" is weaker than a paragraph that shows it. Include 3-5 examples using this structure:

```xml
<context>
Audience: Senior partner reviewing a draft motion
Purpose: Argue that a discovery request is overbroad
Constraints: 1 paragraph, under 100 words
</context>

<example_text>
The request seeks "all documents relating to" the defendant's hiring
practices over a ten-year period. That covers personnel files,
internal emails, training materials, and performance reviews for
roughly 3,000 employees. The relevant period is 2021-2023. The
relevant employees number fewer than 40. We move to compel a
narrowed request limited to the employees and timeframe at issue.
</example_text>

<notes>
- Opens with the specific problem, not procedural background
- Quantifies everything (10 years, 3,000 employees, 2021-2023, 40)
- Four sentences, no hedging
- Ends with the ask, not a recitation of the standard
</notes>
```

Vary the examples by context (brief, memo, client letter, scholarly writing). They are the difference between a vague style guide and one the AI can actually use.

**5. Load it into a persistent Project -- not a chat.** The voice file only works if it loads at the start of every conversation. Pasting it into a one-off chat loses it when you close the tab.

- **Claude.ai**: Click **New Project** -> open Project Settings -> paste your voice file into **Instructions**. Every conversation inside the project inherits it.
- **ChatGPT**: Click **Projects** -> create a project -> paste into the **Instructions** field.
- **Claude Code**: Save your voice file to `~/.claude/rules/` and it auto-loads every session. Or paste it directly into your project's `CLAUDE.md` file. See [Your CLAUDE.md](../toolkit/claude-md.md) for details.

Then test it: ask the AI to write something you have already written -- a paragraph from a recent brief, a memo introduction. Compare the output to the original. If it uses words you would never use, the voice file needs a rule.

??? tip "Multiple writing contexts"
    If your brief writing voice sounds nothing like your scholarly writing voice, you might want separate files -- or a single file with register sections. Keep universal rules (ban list, sentence-length targets) in one place, and context-specific rules in their own sections. For example: one section for litigation writing, one for law review articles, one for client correspondence.

---

## Why Examples Beat Rules

Rules tell the AI what to do. Examples show it what the result looks like. The AI pattern-matches against examples far more reliably than it follows abstract instructions. This is why step 4 matters more than step 3, and why 3-5 annotated examples produce better results than a longer rules list.

The `<context>` tag tells the AI the conditions under which this voice applies. The `<notes>` tag teaches it what to notice. Without both, the AI treats examples as decoration rather than evidence.

---

## Improve It Over Time

Every bad draft teaches you something about your voice file. When the AI gets your voice wrong, do not just fix the output -- fix the file. Voice drift -- where the model shifts register mid-document or across sessions -- is the primary long-term failure mode. It is structural, not a sign that your file is broken. It means the file needs another example or a more specific rule.

| What the AI got wrong | What that reveals | Rule to add |
|---|---|---|
| Used "furthermore" and "moreover" | Ban list is incomplete | Add those transitions to the ban list |
| Long compound sentences | Sentence-length rule too vague | "Cap at 20 words. Vary rhythm: short, short, medium." |
| Hedged where you would be direct | Missing stance rule | "Lead with the conclusion. 'The court should' not 'it could be argued'" |
| Academic tone in a client letter | Missing register distinction | Add a context-specific example for client correspondence |

After 3-4 writing sessions of active updating, most users find the file becomes reliable.

---

## Next Steps

<div class="grid cards" markdown>

-   **AI Project Folders**

    ---

    The same "store it as a file" pattern applied to case research, compliance analysis, and recurring legal tasks.

    [:octicons-arrow-right-24: AI Project Folders](project-folders.md)

-   **Prompt Engineering**

    ---

    Structured prompts with your voice file loaded get better results than either alone.

    [:octicons-arrow-right-24: Prompt Engineering](prompting.md)

-   **ChatGPT vs Claude**

    ---

    Which tool handles voice files better? An honest comparison.

    [:octicons-arrow-right-24: ChatGPT vs Claude](chatgpt-vs-claude.md)

</div>
