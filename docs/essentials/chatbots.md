# Chatbots Done Right

<span class="badge-gold">No Claude Code required</span>

Most people use AI chatbots like Google: one question, one answer, move on. That is the least valuable way to use them.

This page covers the techniques that separate casual users from people who get genuinely useful work out of AI chatbots -- with examples drawn from legal research, writing, and teaching.

!!! workshop "Workshop Session 1"
    We cover this material in the first workshop session. If you are following along on your own, budget about 30 minutes and have a Claude or ChatGPT subscription open in another tab.

---

## Pick the Right Model

This is the single highest-leverage thing most people are not doing.

Every major AI provider offers multiple models at different capability levels. The default is usually *not* the best one. It is the cheapest one they can serve at scale.

| Provider | Weaker Default | Stronger Option | How to Switch |
|----------|---------------|----------------|---------------|
| **Claude** | Sonnet 4.6 (the default on free/Pro) | Opus 4.6 (more capable, slower) | Click the model selector in Claude.ai, or use `/model opus` in Claude Code |
| **ChatGPT** | GPT-4o (the default) | o1-pro or o3 (stronger reasoning) | Click the model dropdown in ChatGPT |

**The practical difference:** For quick questions, the default model is fine. For anything that requires reasoning, synthesis, or careful writing -- a case analysis memo, a summary of competing regulatory frameworks, a draft research proposal -- the stronger model produces noticeably better results. It is the difference between a first-year associate and a senior colleague.

*Model names change frequently. The principle holds: always choose the strongest option in the model selector. Opus-tier models require a paid plan.*

**Cost reality:** Stronger models are either restricted to paid tiers or use more of your usage allowance. But if you are already paying for a subscription, you are leaving money on the table by not using the best model available to you.

---

## Give It Context About You

A chatbot with no context about you gives generic advice. A chatbot that knows your role, your research area, and your preferences gives advice you would actually follow.

### The Basics: Just Tell It

At the start of any conversation, spend 30 seconds on context:

> *I'm a law professor specializing in environmental regulation. I teach two sections of Administrative Law and run a research project on state-level climate litigation. I'm drafting a law review article on agency deference after the Loper Bright decision.*

Now every response is calibrated to your actual situation instead of a generic "legal professional."

### The Power Move: Saved Context

Both Claude and ChatGPT let you save persistent context that applies to every conversation:

| Platform | Feature | Where to Set It |
|----------|---------|----------------|
| **Claude.ai** | Projects | Create a Project, add instructions and files. Every conversation in that project starts with your context. |
| **ChatGPT** | Custom Instructions + Memory | Settings > Personalization > Custom Instructions. Applies to all conversations. ChatGPT also builds memory from your conversations over time. |

**What to put in saved context:**

- Your role and area of specialization
- Your current projects (brief descriptions)
- Your preferences (writing style, level of detail, how you like feedback)
- Common tasks you will ask about

**Example** (for a Claude.ai Project called "Law Review Writing"):

```text
I'm a law professor at a research university specializing in
constitutional law and federal courts. I write 1-2 law review
articles per year and frequently draft amicus briefs.

My writing style: Direct, argument-first, short paragraphs. Precise
legal terminology but accessible to an educated general reader.
Bluebook citations required.

Current projects in progress:
- Article on standing doctrine evolution post-TransUnion. Target:
  top-20 law review. Draft due September.
- Amicus brief on qualified immunity case pending cert. Filing
  deadline April 15.

When I ask for help with writing:
- Always lead with the strongest legal argument
- Flag where my analysis has gaps in authority
- Keep paragraphs under 5 sentences
- Tell me if a section reads more like a treatise than an argument
```

With this in place, every conversation in that project starts with full context.

### The Next Level: Teach It Your Voice

Saved context tells the AI *about* you. A voice file teaches it to *write like* you. If AI output never quite sounds right -- too formal, too hedgy, full of words you would never use -- the fix is a reference document that captures your actual patterns. [:octicons-arrow-right-24: Teaching AI Your Voice](voice.md)

### The Next Level: Project Folders

Saved context gets you started. But for recurring tasks -- case research, client intake protocols, regulatory compliance analysis -- you can go further: a canonical file that stores your stable preferences, constraints, and past results so every new conversation starts from a consistent baseline and improves over time.

[:octicons-arrow-right-24: Build an AI Project Folder](project-folders.md)

---

## Structure Your Requests

Structured prompts get dramatically better results.

**The pattern:**

1. **Context** -- what the AI needs to know about the situation
2. **Task** -- what you want it to do (be specific)
3. **Format** -- how you want the output structured
4. **Constraints** -- length, tone, what to avoid, what to prioritize

**Weak prompt:**
> *Help me write a memo about qualified immunity.*

**Strong prompt:**
> *Write a 1,500-word legal research memo analyzing whether the qualified immunity defense applies to school resource officers who use physical force during student disciplinary encounters. Focus on the circuit split between the Fourth and Ninth Circuits. The audience is a supervising partner at a civil rights litigation firm. Lead with the conclusion, then the legal standard, then the circuit analysis, then practical implications. Use Bluebook citation format. Avoid treatise-style exposition -- this should read like a working memo, not a law review article.*

The second version takes 60 seconds longer to write and saves 20 minutes of back-and-forth. For the full six-section framework with examples, see [Prompt Engineering](prompting.md).

---

## Use Conversations, Not One-Shots

Chatbots have memory within a conversation. Use it.

**The one-shot mistake:** Asking one big question, getting one long answer, starting a new conversation for the next question.

**The conversational approach:** Build up context through a series of exchanges.

```text
You:    Here's my draft argument section on standing. What are
        the weakest points?
Claude: [identifies 3 issues]
You:    Rewrite the paragraph addressing Article III injury-in-fact.
        Keep my analytical voice.
Claude: [rewrites]
You:    Good direction, but too formal. I want it to sound more like
        my brief writing -- shorter sentences, punchier transitions.
Claude: [revises]
You:    Perfect. Now do the same for the causation analysis.
```

Each exchange builds on the last. The AI learns your preferences *within the session* and gets better as you go. This is dramatically more effective than starting fresh each time.

---

## Know What Chatbots Are Bad At

Being honest about limitations saves more time than any prompting technique.

**Chatbots are unreliable for:**

- **Legal citations** -- They hallucinate case names, invent holdings, and fabricate docket numbers with complete confidence. **Always verify every citation.** This is the single most dangerous failure mode for legal professionals. We discuss this further below.
- **Factual claims** -- They state falsehoods confidently. Always verify facts, especially numbers and dates.
- **Math** -- Do not trust arithmetic in conversational responses. For any calculation that matters, ask the chatbot to write and run code, or verify externally.
- **Current events** -- Training data has a cutoff. Web search features help but are not comprehensive.

**Chatbots are genuinely good at:**

- **Drafting and editing** -- First drafts of memos and briefs, rewrites, tone adjustments, structural suggestions
- **Synthesis** -- Combining multiple sources or arguments into coherent summaries
- **Brainstorming** -- Generating counterarguments, identifying issues you had not considered
- **Explaining** -- Breaking down complex doctrinal areas for different audiences (students, clients, judges)
- **Format conversion** -- Turning notes into structured memos, bullets into prose, case holdings into comparison tables

**The right mental model:** A chatbot is a brilliant, well-read colleague with no memory and a tendency to make things up. Trust the reasoning, verify the facts.

---

## The Hallucinated Citations Problem

This deserves its own section because it is uniquely dangerous for legal work.

AI chatbots will confidently generate citations that look perfectly real -- correct Bluebook format, plausible-sounding case names, realistic volume and page numbers -- but point to cases that do not exist. Lawyers have already been sanctioned for filing briefs with AI-generated fake citations. This is not an occasional glitch; it is a fundamental property of how these models work.

**Rules for legal citations with AI:**

1. **Never cite a case you have not verified in Westlaw, Lexis, or another authoritative database.** No exceptions.
2. **If the AI provides a citation, treat it as a research lead, not a source.** Look it up. Confirm the holding matches what the AI described.
3. **Ask the AI to flag its own uncertainty.** Add to your prompt: *"If you are not certain a case exists or that its holding matches your description, say so explicitly rather than guessing."*
4. **Use AI for analysis, not citation generation.** AI is excellent at structuring arguments, identifying relevant doctrinal frameworks, and suggesting research directions. It is unreliable as a citation finder.

!!! ask-claude "Try this now"
    Ask Claude or ChatGPT to list five landmark cases on a topic in your area. Then verify each one in Westlaw or Lexis. How many are real? How many have the holding the AI described? This exercise takes 10 minutes and will permanently calibrate your trust level.

---

## Build a Library of Good Prompts

When you find a prompt that works well for a recurring task, save it. Build a personal collection.

Start simple -- a text file, a note in your phone. Just stop reinventing the wheel every time you need to:

- Draft a case brief summary for class
- Analyze a contract clause for potential issues
- Turn seminar notes into a research agenda
- Review a draft article section for logical gaps
- Generate exam hypotheticals from a set of doctrinal rules

Over time, this library becomes the seed of something more powerful. On this site, the [Setup Guide](../setup/index.md) shows how to turn saved prompts into automated skills that run in seconds. But even without that, a simple collection of your best prompts is one of the highest-value things you can build.

---

## Next Steps

<div class="grid cards" markdown>

-   **Level up your prompts**

    ---

    Prompt engineering as a structured skill, not just tips and tricks.

    [:octicons-arrow-right-24: Prompt Engineering](prompting.md)

-   **Teach AI your voice**

    ---

    Build a voice file so your memos and scholarship sound like you, not like every other AI output.

    [:octicons-arrow-right-24: Teaching AI Your Voice](voice.md)

-   **Understand the landscape**

    ---

    Honest comparison of when to use which tool for legal work.

    [:octicons-arrow-right-24: ChatGPT vs Claude](chatgpt-vs-claude.md)

-   **Stress-test your plans**

    ---

    Paste a plan into a fresh AI chat with an adversarial prompt and get structured critique -- no coding needed.

    [:octicons-arrow-right-24: Plan Review (Browser)](../workflows/plan-review-browser.md)

-   **Go deeper**

    ---

    When chatbots are not enough, Claude Code turns AI into a workflow tool.

    [:octicons-arrow-right-24: Get Started](../setup/index.md)

</div>
