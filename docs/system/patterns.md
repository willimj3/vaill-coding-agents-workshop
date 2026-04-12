# Patterns and Templates

Reusable design patterns for workflows and custom tools. These show up repeatedly in well-designed Claude Code workflows -- whether you are building a case briefing assistant, a memo template, or a research pipeline.

---

## Structural Patterns

### Phased Execution

Break complex workflows into phases with user checkpoints between them.

```markdown
### Phase 1: Discovery
[Assess current state — read files, ask questions]

### Phase 2: Analysis
[Present findings, identify gaps]

**STOP: Discuss with user before proceeding.**

### Phase 3: Proposal
[Present specific plan based on discussion]

**Ask for approval before Phase 4.**

### Phase 4: Implementation
[Execute the approved plan]
```

**When to use:** Any workflow where executing the wrong thing is hard to undo. Document reorganization, syllabus restructuring, bulk file operations.

**Law faculty example:** A case briefing workflow that (1) reads the opinion, (2) identifies the key holdings and reasoning, (3) presents a draft brief for your review, then (4) formats it into your preferred template -- only after you confirm the analysis is correct.

---

### Flags Parsing

Parse arguments to control workflow behavior without separate commands.

```markdown
## Arguments

`$ARGUMENTS` supports:
- `quick` — abbreviated output
- `depth:light/standard/deep` — thoroughness level
- `file:path/to/file` — explicit input file
- `focus:dimension` — weight one aspect
- `format:memo/brief/outline` — output format
- `help` — show options and stop
```

**When to use:** Workflows with multiple modes or configurable behavior. Keeps one workflow flexible instead of creating five variations.

**Law faculty example:** A research summary workflow that accepts `depth:light` for a quick overview of a case or `depth:deep` for a full analysis with procedural history, reasoning, and implications for your article.

---

### Critic Stance

Explicitly shift Claude's role from collaborator to critic. Counteracts the tendency to be agreeable.

```markdown
**CRITIC STANCE:**
> You are now the critic, not the drafter. Do not rationalize. Do not
> hedge. Your job is to find what's missing, what will break, and what's
> wishful thinking. If you drafted this document earlier in the session,
> that makes you *more* responsible for finding its flaws, not less.
```

**When to use:** Review and critique tasks where you want honest assessment, not validation. Especially important when Claude is reviewing its own work (though an agent is even better for this -- see [Skills and Agents Explained](agents-vs-skills.md)).

**Law faculty example:** After Claude drafts an exam question, switch to critic stance and ask it to identify ambiguities, unintended answer paths, and whether the question actually tests the learning objectives you specified.

---

### Output Templates

Define the exact format of workflow output for consistency.

```markdown
### Output

```
CASE BRIEF — [Case Name]
Citation: [Full citation]

PROCEDURAL POSTURE
[How the case arrived at this court]

ISSUE(S)
1. [Issue]

HOLDING
[Court's answer to each issue]

REASONING
[Key analytical steps]

SIGNIFICANCE
[Why this case matters for the course/article]
```
```

**When to use:** Any workflow that produces structured output. Consistent format makes it easier to scan results across runs and compare outputs.

**Law faculty example:** A committee report template that always includes an executive summary, background, analysis, recommendation, and dissenting views section -- so every committee memo your workflow produces has the same professional structure.

---

### Iteration Gate

After producing output, explicitly ask whether to proceed, adjust, or stop.

```markdown
After presenting the draft, ask:
> "Revise this? Or provide feedback to refine further."

User can:
- **Accept** — finalize the document
- **Give feedback** — loop back with adjustments
- **Dismiss** — end without changes
```

**When to use:** Any workflow that proposes changes the user should review before they take effect.

**Law faculty example:** A student feedback workflow that drafts comments on a paper, then pauses so you can review the tone, adjust the emphasis, and confirm before moving to the next paper.

---

## Behavioral Patterns

### Depth Calibration

Adjust how thoroughly Claude engages based on task importance.

| Level | Behavior | Default? |
|-------|----------|----------|
| **Light** | Format only, no extras | Yes |
| **Standard** | Add assumptions and rationale | No |
| **Deep** | Research, compare, and verify | No |

**When to use:** Workflows that handle tasks ranging from trivial to high-stakes. Avoids over-engineering simple requests while providing rigor when it matters.

**Law faculty example:** A memo-drafting workflow where `light` produces a quick summary paragraph, `standard` adds supporting analysis, and `deep` includes counterarguments and citations to relevant authority.

---

### Graceful Degradation

When an MCP integration or file is missing, explain what is unavailable and proceed with what is possible.

```markdown
## Error Handling

- **Gmail MCP not available:** "Gmail access is not configured. I can
  still draft the memo based on the files in this folder. To enable
  email features, see the MCP setup guide."
- **File not found:** "Expected [file] at [path]. Proceeding without
  it — [what changes]."
```

**When to use:** Any workflow that depends on MCP integrations or external files. Users should not hit a dead end because one component is missing.

**Law faculty example:** A daily briefing workflow that checks email, calendar, and project files. If Gmail is not connected, it still summarizes your calendar and recent file changes -- just without the email component.

---

### Domain Auto-Detection

Infer the right behavior from content rather than requiring explicit flags.

```markdown
Infer the domain from content:
| Signals in content | Behavior |
|-------------------|----------|
| Case citations, statutory references | Use legal analysis approach |
| "syllabus", "learning objectives" | Use course design approach |
| "committee", "recommendation" | Use memo/report approach |
| "draft", "article", "law review" | Use scholarly writing approach |
```

**When to use:** Workflows that work across different types of legal work. Reduces the arguments users need to remember.

**Law faculty example:** A general "help me with this document" workflow that detects whether you have handed it a case opinion, a syllabus, a committee memo, or an article draft -- and adjusts its approach accordingly.

---

## Example Workflows for Law Faculty

These are not installable tools -- they are patterns you can ask Claude to help you build. Each one illustrates several of the patterns above working together.

### Case Briefing Workflow

**Patterns used:** Phased Execution, Output Template, Depth Calibration

Ask Claude to read a case opinion (from a file on your computer or pasted text) and produce a structured brief. The workflow:

1. Reads the full opinion
2. Identifies parties, procedural posture, issues, holdings, and reasoning
3. Presents a draft brief in your preferred format
4. Asks for your review before finalizing
5. Optionally adds teaching notes (what to emphasize in class, potential exam issues)

To get started, try telling Claude:

> "I want to create a case briefing workflow. Read the patterns page on my workshop site for the structure, then help me build one that produces briefs in [your preferred format]."

### Research Assistant Pattern

**Patterns used:** Flags Parsing, Critic Stance, Iteration Gate

A workflow for literature review and research synthesis:

1. Takes a research question or topic as input
2. Searches your Zotero library (if connected) for relevant sources
3. Reads and summarizes each source
4. Identifies themes, conflicts, and gaps in the literature
5. Produces an annotated bibliography or literature review section
6. Switches to Critic Stance to identify what the review missed

### Student Feedback Pipeline

**Patterns used:** Phased Execution, Output Template, Graceful Degradation

A workflow for batch processing student papers:

1. Reads a rubric document you provide
2. For each student paper in a folder, produces structured feedback
3. Flags common issues across the class
4. Generates a summary of class-wide patterns for your review
5. If the rubric file is missing, asks you to describe your criteria and proceeds

---

## Quality Checklist

Before relying on any workflow, verify:

- [ ] **Does it work with no arguments?** The zero-argument case should be the most common use.
- [ ] **Is the output format specified?** Do not let Claude decide how to format results.
- [ ] **Does it handle errors?** Missing files, missing MCP, empty input.
- [ ] **Is it focused?** Does one thing well, not three things poorly.
- [ ] **Are arguments documented?** Users should not have to read the instructions to know what options exist.
- [ ] **Has it been tested with real tasks?** Not just the happy path.
- [ ] **Does it fail gracefully when MCP is unavailable?** If it uses MCP, what happens without it?
- [ ] **Does it pause for review before making changes?** Especially important for workflows that edit files or send emails.
