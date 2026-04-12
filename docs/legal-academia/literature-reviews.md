# Literature Reviews

**Using AI to survey legal scholarship, synthesize findings, and identify gaps — then verifying everything in HeinOnline and Westlaw.**

A literature review is one of the most time-consuming parts of legal scholarship. We read dozens or hundreds of articles, track who said what, identify where the conversation stands, and figure out what has not been said yet. AI does not replace that intellectual work, but it dramatically accelerates the early stages — identifying relevant sources, summarizing arguments, and organizing themes so we can focus our reading time on the articles that actually matter.

!!! warning "The foundational rule"
    AI models hallucinate citations. They will invent article titles, attribute arguments to the wrong scholars, and fabricate journal volume numbers. Every citation AI generates is a lead, not a fact. Verify every source in HeinOnline, Westlaw, or your library's database before relying on it. This is not a minor caveat — it is the single most important thing on this page.

---

## Why This Matters

The traditional literature review process looks like this: start with a few known articles, follow their citations, run keyword searches in legal databases, read abstracts, skim promising pieces, read closely, take notes, organize by theme, identify gaps. It works, but the search-and-skim phase can take weeks.

AI compresses that early phase. In a single conversation, we can:

- Generate a structured overview of scholarship in a field
- Identify major schools of thought and their key proponents
- Surface arguments and counterarguments we might have missed
- Organize sources by theme, methodology, or conclusion
- Highlight gaps — questions the literature has not adequately addressed

The catch: the AI's knowledge has a training data cutoff. It may not know about articles published in the last six to twelve months. And it may confidently describe articles that do not exist. That is why we treat AI output as a research map, not a finished bibliography.

---

## The Workflow

### Step 1: Define your research question

Before asking AI to survey a field, be specific about what you are looking for. A vague prompt produces a vague survey. A precise prompt produces something you can actually work with.

**Too vague:**

```text
What has been written about AI and the law?
```

**Specific enough to be useful:**

```text
I am writing a law review article about the use of algorithmic risk
assessment tools in pretrial detention decisions. I need to understand
the current state of legal scholarship on this topic.

Survey the legal academic literature on algorithmic risk assessment
in pretrial bail and detention. Organize your response by:

1. Constitutional challenges (due process, equal protection)
2. Empirical studies on accuracy and bias
3. Proposed regulatory frameworks
4. Comparative approaches (state-by-state variation)

For each theme, identify the major positions, name the key scholars,
and cite specific articles where possible. Flag any significant
disagreements or unresolved questions in the literature.
```

The second prompt gives the AI enough structure to produce a genuinely useful overview. It specifies the sub-questions, asks for organization by theme, and explicitly requests identification of disagreements and gaps.

### Step 2: Generate the initial survey

Paste your prompt into Claude or ChatGPT. For a broad initial survey, we recommend starting with **ChatGPT Deep Research** — it can search the web, access recent publications, and compile a detailed report with links. This is one of the areas where ChatGPT's browsing capability gives it a meaningful edge over Claude for the initial discovery phase.

!!! tip "ChatGPT Deep Research for literature surveys"
    ChatGPT's Deep Research mode (available on Plus and Pro plans) can produce detailed research reports that would take hours to compile manually. Give it a specific, well-structured prompt and it will search across sources, synthesize findings, and provide links. The output is not perfect — it still requires verification — but it is a dramatically faster starting point than manual searching. See our [ChatGPT vs Claude](../essentials/chatgpt-vs-claude.md) page for when each tool works best.

For a more analytical synthesis — organizing themes, comparing arguments, identifying logical gaps — Claude tends to produce more structured and nuanced output. A practical workflow: use ChatGPT Deep Research for the initial survey, then paste the results into Claude for deeper analysis and organization.

### Step 3: Summarize and synthesize

Once you have an initial list of sources (whether from AI, your own knowledge, or both), ask the AI to help you organize and synthesize. This is where AI adds the most value — not in finding sources, but in helping you see patterns across them.

```text
Here are 15 articles I have identified on algorithmic risk assessment
in pretrial detention. For each, I am pasting the title, author, and
a brief description of the argument.

[Paste your article list here]

Now:
1. Group these into 3-5 thematic clusters based on their core arguments
2. For each cluster, identify the dominant position and any dissenting views
3. Identify which pairs of articles are in direct conversation with each other
4. Flag any obvious gaps — arguments or perspectives that seem missing
   from this collection
5. Suggest 3-5 additional search terms I should try in HeinOnline to fill
   those gaps
```

### Step 4: Identify gaps

Gap identification is one of the highest-value uses of AI in literature reviews. After you have built your source list and organized it by theme, ask the AI to look for what is missing.

```text
Based on the literature survey above, identify:

1. Questions that multiple authors raise but none adequately answer
2. Methodological approaches that have not been tried
   (e.g., if all studies are doctrinal, note the absence of empirical work)
3. Jurisdictions or contexts that are underrepresented
4. Arguments that seem logically necessary but that no one has made
5. Potential connections to scholarship in adjacent fields
   (criminal justice, data science, administrative law) that legal
   scholars have not drawn

For each gap, explain why it matters and suggest how a new article
could address it.
```

This prompt often surfaces genuinely useful research directions. The AI can identify patterns across a body of work that are difficult to see when reading articles one at a time.

### Step 5: Verify in HeinOnline and Westlaw

This step is not optional. For every citation the AI generated:

1. **Search the exact title** in HeinOnline or your library's database
2. **Confirm the author, journal, volume, and year** match what the AI claimed
3. **Read the abstract** to confirm the AI's characterization of the argument is accurate
4. **Flag any source you cannot find** — it may be hallucinated entirely

In our experience, AI-generated literature surveys typically contain 10-30% hallucinated or inaccurate citations. The percentage varies by how well-known the field is and how recent the scholarship. Obscure topics and very recent publications have higher hallucination rates.

!!! tip "A time-saving verification workflow"
    Rather than checking every citation individually, batch your verification. Export the AI's citation list, sort by journal, and run targeted searches in HeinOnline. You will quickly see which citations are real and which are fabricated. For the real ones, skim the abstracts to confirm the AI's characterization. This batch approach typically takes 30-60 minutes for a 20-article list — much faster than building the list from scratch, even accounting for the verification step.

---

## Limitations

**Training data cutoff.** AI models have a knowledge cutoff date. Articles published after that date will not appear in the AI's survey unless you are using a tool with web browsing (like ChatGPT Deep Research). Always supplement AI surveys with a current database search.

**Hallucinated citations.** This bears repeating: AI models will invent citations that look entirely plausible — correct journal name, reasonable author, believable title. The only defense is verification. Do not cite anything you have not confirmed exists.

**Characterization errors.** Even when the AI cites a real article, it may misstate the author's argument. Read the actual article before relying on the AI's summary of it.

**Bias toward prominent scholarship.** AI models tend to surface well-known articles and established scholars. Newer voices, working papers, and scholarship in specialized journals may be underrepresented. Supplement with targeted database searches.

**No Bluebook formatting.** AI-generated citations rarely conform to proper legal citation format. Plan to format all citations yourself or use a citation manager.

---

## Project Folder Template

If you do literature reviews regularly, create a dedicated project folder (in ChatGPT Projects or Claude.ai Projects) with standing instructions. Here is a template you can adapt:

```text
# Literature Review Assistant

## My role
I am a law professor researching [your field]. I publish in [types of
journals]. My current research focuses on [specific topics].

## How to help me
- When I ask you to survey a topic, organize by theme and identify
  major positions, key scholars, and areas of disagreement
- Always distinguish between what you know from training data and
  what you are inferring or speculating about
- When citing articles, include: author, title, journal, volume, year,
  and starting page if known
- Flag explicitly when you are uncertain about a citation
- Suggest search terms for HeinOnline and Westlaw that I can use
  to verify and extend your suggestions

## Rules
- Never present a citation as confirmed unless I have told you I verified it
- Do not hallucinate details — if you are unsure about a volume number
  or year, say so
- When I paste a list of sources, help me organize and synthesize them;
  do not just summarize each one individually
- Prioritize identifying gaps and unresolved questions over comprehensive
  coverage of settled issues

## My verification workflow
I verify all citations in HeinOnline before using them. When you
generate citations, format them as a checklist I can work through
during my verification pass.
```

Load this into a project and every new literature review conversation starts with these instructions. Update the file as you learn what works — after three or four reviews, the instructions will stabilize and updates will be a line or two at most.

---

## When to Use Which Tool

| Task | Best Tool | Why |
|------|-----------|-----|
| Initial broad survey | ChatGPT Deep Research | Web browsing finds recent work |
| Thematic organization | Claude | More structured analytical output |
| Gap identification | Claude | Stronger at logical analysis |
| Citation verification | HeinOnline / Westlaw | Only reliable source for legal citations |
| Ongoing research tracking | Project folder (either platform) | Persistent context across sessions |

---

## Next Steps

<div class="grid cards" markdown>

-   **Structure your prompts**

    ---

    The prompting techniques that make literature review prompts more effective.

    [:octicons-arrow-right-24: Prompt Engineering](../essentials/prompting.md)

-   **Build a research project folder**

    ---

    Store your research preferences, verification workflows, and field context in a reusable file.

    [:octicons-arrow-right-24: AI Project Folders](../essentials/project-folders.md)

-   **Move to empirical work**

    ---

    When your literature review reveals empirical gaps, AI can help you design and execute the study.

    [:octicons-arrow-right-24: Empirical Legal Research](empirical-research.md)

</div>
