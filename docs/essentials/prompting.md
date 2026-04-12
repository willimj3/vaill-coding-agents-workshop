# Prompt Engineering

<span class="badge-gold">No Claude Code required</span>

Prompt engineering sounds technical. It is not. It is the skill of asking AI tools for what you actually want, in a way that gets useful results on the first try.

This page covers prompt engineering as a repeatable method you can apply to any legal task.

!!! tip "The single most important thing on this page"

    Do not memorize prompt engineering rules -- **make the AI do it for you.**
    Create a Project in [ChatGPT](https://chatgpt.com) or
    [Claude.ai](https://claude.ai), paste in the instructions below, and it
    will restructure your messy input into clean prompts automatically.
    [Jump to the how-to.](#make-the-ai-do-this-for-you)

    The same idea works for plan review: paste a plan into a
    [fresh chat with an adversarial prompt](../workflows/plan-review-browser.md)
    and get structured critique -- no coding needed.

!!! workshop "Workshop Session 1"
    We walk through the prompt framework live and build at least one legal prompt together. Bring a real writing task -- a memo topic, a research question, a brief section -- and we will structure it using the six-section method below.

---

## Why This Matters

The gap between a mediocre AI interaction and a great one is almost always the prompt. Not the model, not the subscription tier, not some secret technique. Just how clearly you communicated what you wanted.

Good prompts share three properties:

1. **They provide context** -- enough background that the AI does not have to guess
2. **They specify the task** -- unambiguously, in 1-2 sentences
3. **They define the output** -- format, length, tone, audience

Most bad interactions fail on #1 (no context) or #3 (no output specification).

---

## The Anatomy of a Good Prompt

Here is a real prompt with each section labeled. Not every prompt needs all six parts -- but knowing them lets you diagnose why a prompt is not working.

=== "Full example (labeled)"

    !!! example "Role"
        You are a senior litigation partner reviewing a draft memo prepared by a junior associate. You have 25 years of experience in complex commercial litigation.

    !!! info "Context"
        I am drafting a legal research memo on whether a forum-selection clause in a software licensing agreement is enforceable when the end user is a state government entity claiming sovereign immunity. The memo is for the partner leading the case. The client is the software vendor seeking to enforce the clause.

    !!! success "Task"
        Draft the analysis section (800-1000 words). Focus on the enforceability framework under *M/S Bremen v. Zapata* and its progeny, the sovereign immunity complications, and the circuit-specific treatment in the Fifth Circuit.

    !!! warning "Constraints"
        - Keep it under 1000 words
        - Analytical but direct -- like a working memo, not a law review article
        - Do not include the factual background -- that is a separate section
        - Focus on the strongest arguments for enforceability. Address counterarguments but do not lead with them.

    !!! quote "Output Format"
        Structure as: (1) Conclusion, (2) Legal standard for forum-selection clauses, (3) Sovereign immunity complication, (4) Fifth Circuit treatment. Use short paragraphs. Bluebook citations required. No bullet points in the analysis -- this is narrative prose.

    !!! tip "Bookend"
        Remember: the goal is a working litigation memo, not scholarship. Keep the tone practical and emphasize what the court is most likely to do, not every theoretical possibility.

=== "Just the prompt (copy-paste)"

    ```text
    You are a senior litigation partner reviewing a draft memo
    prepared by a junior associate. You have 25 years of experience
    in complex commercial litigation.

    I am drafting a legal research memo on whether a forum-selection
    clause in a software licensing agreement is enforceable when the
    end user is a state government entity claiming sovereign immunity.
    The memo is for the partner leading the case. The client is the
    software vendor seeking to enforce the clause.

    Draft the analysis section (800-1000 words). Focus on the
    enforceability framework under M/S Bremen v. Zapata and its
    progeny, the sovereign immunity complications, and the
    circuit-specific treatment in the Fifth Circuit.

    Constraints:
    - Keep it under 1000 words
    - Analytical but direct -- like a working memo, not a law review
    - Do not include the factual background
    - Focus on strongest arguments for enforceability; address
      counterarguments but do not lead with them

    Structure as: (1) Conclusion, (2) Legal standard for
    forum-selection clauses, (3) Sovereign immunity complication,
    (4) Fifth Circuit treatment. Use short paragraphs. Bluebook
    citations. No bullet points -- narrative prose.

    Remember: the goal is a working litigation memo, not scholarship.
    Keep the tone practical and emphasize what the court is most
    likely to do.
    ```

### The six sections explained

**1. Role** (optional) -- Tell the AI what perspective to take. Useful when you need domain expertise or a particular evaluative lens. Skip for simple tasks -- "You are a helpful assistant" adds nothing.

**2. Context** -- What does the AI need to know? Your role, the legal issue, relevant constraints, what you have already decided.

**3. Task** -- The core ask in 1-2 clear sentences. Front-load this -- do not bury it after three paragraphs of context.

**4. Constraints** -- What should the AI do or avoid? Be specific: "Keep it under 1000 words" not "be concise." Include exclusions and priorities.

**5. Output Format** -- How should the result be structured? Sections, length, tone, citation style.

**6. Bookend** (for long prompts) -- Restate the key instruction at the end. AI models sometimes lose focus on long inputs.

---

## Match Effort to Stakes

Not every task needs the same level of effort. A quick email to a colleague does not need the AI to "research best practices." A motion to dismiss does.

**Three levels:**

| Level | When to Use | What to Add |
|-------|-------------|-------------|
| **Light** | Quick tasks, routine emails, simple lookups | Nothing extra -- just format clearly |
| **Standard** | Case analysis, memos, research summaries | Ask for assumptions and rationale: *"Include key assumptions (2-3 bullets) and brief rationale for major analytical choices."* |
| **Deep** | Briefs, motions, law review articles, grant proposals | Ask for verification: *"Research current case law on this issue. Compare your analysis against the leading treatise treatment. Flag where you deviate and why."* |

**Default to Light.** Upgrade when the stakes justify it.

---

## Use Examples (But Try Without Them First)

Examples are one of the most powerful prompting techniques -- but they are also overused. The rule of thumb: **try without examples first.** If the output format or style is wrong, tighten your instructions or add an output schema. Only add examples if that still fails.

When examples help most:

- You need a specific format the AI does not know (a firm's internal memo template, your law school's syllabus format)
- You want consistent voice across multiple outputs
- Describing the format in words would take longer than showing it

When you probably do not need them:

- Standard formats (emails, case briefs, bullet-point summaries) -- the AI already knows these
- Tasks where you want the AI to suggest the best approach rather than match a template

When you do use examples, keep them compact. `input -> output` pairs work better than verbose multi-paragraph samples. Two good examples beat five mediocre ones.

---

## Use Tags to Separate Instructions from Content

When you paste a long document into a chat, the AI can confuse your instructions with the document text. Simple tags fix this:

```text
<instructions>
Analyze this contract clause for potential ambiguities and
enforceability risks under New York law. Focus on the
indemnification and limitation-of-liability provisions.
Keep it under 500 words.
</instructions>

<contract_clause>
[Full clause text pasted here...]
</contract_clause>

<output_format>
Three sections: (1) Key ambiguities, (2) Enforceability risks,
(3) Recommended revisions.
</output_format>
```

Without tags, the AI has to figure out where your instructions end and the document begins. With tags, there is no ambiguity. You do not need tags for short, simple prompts -- they are most useful when you are mixing instructions with pasted content.

---

## Break Complex Tasks into Steps

A prompt that asks for a full brief -- statement of facts, legal standard, argument, and conclusion -- will produce mediocre versions of all four. Break complex tasks into a sequence of focused prompts where each step builds on the previous one.

**Single prompt (works for simple tasks):**

> Analyze this contract and identify the key risks.

**Chained approach (better for complex work):**

> *Prompt 1:* Read this contract and identify the 5 most significant risk areas for our client (the licensee). For each, quote the relevant clause and explain the risk.
>
> *[Review output, then...]*
>
> *Prompt 2:* For risks #1 and #3, draft revised clause language that addresses the identified issues while remaining commercially reasonable.

Chaining works because you can course-correct between steps. If Prompt 1 misses something, you fix it before Prompt 2 builds on bad foundations. This matters most for legal analysis, brief drafting, and research memos -- anything where direction might shift based on intermediate results.

---

## Common Anti-Patterns

**Vague thoroughness language.** "Be comprehensive" and "be meticulous" are empty calories. Replace with specific verbs:

- "Compare the majority and dissent on the standard of review"
- "Identify the three strongest counterarguments to our position"
- "Flag where our analysis lacks binding authority in this circuit"

**Over-prompting.** Modern AI models are good at following instructions. You do not need `CRITICAL: YOU MUST ABSOLUTELY...` -- a calm, specific directive works better. Shouting in all-caps does not make the AI try harder. In fact, [Anthropic's prompt engineering guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering) specifically warns that anti-laziness prompts like "be thorough" and "think carefully" can cause newer models to overthink and waste time.

**No pushback permission.** If you want honest feedback on a draft, say so: *"Tell me directly if this argument has problems. Do not just agree with my analysis."* By default, AI tends toward politeness and agreement.

---

## Make the AI Do This for You

You do not have to internalize all of the above. Create a project in ChatGPT or Claude.ai with prompt engineering instructions as the project file, and the AI will restructure your messy input into clean prompts automatically.

### Setup

- **ChatGPT** (Plus or Team): Sidebar -> Projects -> New Project -> paste the file below into Instructions.
- **Claude.ai** (Pro): Projects -> Create Project -> paste into Project Instructions.

### The instructions file

The instructions tell the AI to take any unstructured input and restructure it into a clean, well-organized prompt. It supports three modes: "quick format" (just the prompt), "format and critique" (prompt + alternatives), and "prompt pack" (2-4 variants at different depth levels).

Paste the following into your project's instructions field:

```text
You are a prompt engineering assistant for legal professionals.

When I give you a rough description of what I need, restructure it
into a clean prompt using this framework:
1. Role (if useful) -- what perspective the AI should take
2. Context -- background the AI needs
3. Task -- the specific ask in 1-2 sentences
4. Constraints -- what to do and avoid
5. Output format -- structure, length, tone, citation style
6. Bookend (for long prompts) -- restate the key instruction

Three modes:
- "quick" -- just output the formatted prompt
- "critique" -- output the prompt + suggest alternatives
- "pack" -- output 2-4 prompt variants at different depth levels

Default to "quick" unless I specify otherwise.
```

Now when you dump a rough idea into this project -- dictated, messy, whatever -- the AI restructures it into a clean prompt you can paste anywhere.

!!! ask-claude "Try this now"
    Think of a legal task you do regularly -- reviewing a contract section, summarizing a case for class, drafting a research question. Describe it in two or three messy sentences. Paste it into a Claude or ChatGPT project with the instructions above. See what comes back.

---

## Going Further

Once you find prompts that work well for recurring tasks, save them. Replace specifics with `[FILL IN]` placeholders and you have reusable templates.

When you are ready for more: [Project Folders](project-folders.md) show how to build domain-specific instruction sets, and in Claude Code you can turn templates into *skills* (slash commands) that run with a single command -- the [Setup Guide](../setup/index.md) shows how.

### Three levels of saved context

Save context at three levels: a personal prompt library for any chatbot, [Project Folders](project-folders.md) for recurring tasks, or [CLAUDE.md](../toolkit/claude-md.md) for Claude Code. Start with level one and add layers as you need them.

---

## Recommended Resources

- **[Anthropic's Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering)** -- The official reference. Thorough and practical.

---

## Next Steps

<div class="grid cards" markdown>

-   **Build your voice file**

    ---

    Make AI output sound like your writing, not generic AI prose.

    [:octicons-arrow-right-24: Teaching AI Your Voice](voice.md)

-   **Stress-test your plans**

    ---

    Paste a plan into a fresh chat with an adversarial prompt and get structured critique -- no coding needed.

    [:octicons-arrow-right-24: Plan Review (Browser)](../workflows/plan-review-browser.md)

-   **Set up project folders**

    ---

    Turn recurring legal tasks into reusable AI workflows.

    [:octicons-arrow-right-24: AI Project Folders](project-folders.md)

</div>
