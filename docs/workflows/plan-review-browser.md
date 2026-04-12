# Stress-Test Any Plan with a Fresh AI Chat

<span class="badge-teal">No Claude Code required</span>

!!! tip "Use Claude Code? You can do this from the terminal too"
    The workflow on this page works entirely in a browser -- Claude.ai, ChatGPT, or any AI chat tool. If you have Claude Code installed, you can run the same process from the terminal by pasting the prompt below directly into a fresh session. The key insight is the same either way: **the reviewer must not be the author.**

---

## Why a fresh chat?

AI tools are great at helping you *build* plans. They are bad at *critiquing* them -- because the same model that helped develop an idea has a natural bias toward defending it. Researchers call this **sycophancy**: the tendency to agree with whatever the user seems to want ([Anthropic, 2024](https://www.anthropic.com/news/visible-extended-thinking)).

The fix is simple: **finish your plan in one conversation, then paste it into a brand new chat for critique.** The fresh context eliminates anchoring bias -- the reviewer has zero knowledge of your reasoning, compromises, or earlier drafts. It is the AI equivalent of handing your draft to a colleague who was not in the room when you wrote it.

---

## When this is worth doing

- **Brief strategies and motions** -- before filing, get a structured adversarial review
- **Regulatory compliance plans** -- surface gaps in your analysis before the agency does
- **Clinic proposals** -- stress-test a new clinic structure before presenting it to the dean
- **Course redesigns** -- catch logistical problems in a new curriculum before the semester starts
- **Grant applications** -- find weaknesses before the review committee does
- **Hiring plans and committee proposals** -- any faculty governance decision worth getting right

**Skip for:** routine emails, reversible decisions, plans you will iterate on daily anyway.

---

## The method

**1. Finish your plan.** Get it to a state where you think it is ready -- in any tool, on paper, wherever.

**2. Copy it with enough context.** Include: the goal, deadline, available resources, key constraints, stakeholders involved, and what success looks like. A 3-sentence sketch produces a shallow review. Aim for 200+ words with concrete steps.

**3. Open a new chat** in Claude.ai, ChatGPT, or any AI tool. Do not continue in the conversation where you built the plan.

**4. Paste the prompt below, then paste your plan** at the bottom where indicated.

**5. Read the critique, then iterate.** Fix critical issues first. Ask follow-up questions. For high-stakes plans, open *another* fresh chat and run a second review from a different angle.

---

## The prompt

Copy this into your fresh chat, then paste your plan at the bottom:

```text
You are an external reviewer, not a collaborator. Your job is to find
problems, not to encourage.

Stress-test this plan. For each issue, point to the specific step or
sentence that triggered your concern. Classify each finding as:
- MUST FIX -- will likely cause failure or major rework if not addressed
- WORTH CONSIDERING -- creates risk, but the plan can proceed if you
  decide consciously to accept it

Find:
1. The top 3 ways this plan could fail -- work backward from failure
2. What's missing that someone experienced in this domain would expect
   (stakeholders, dependencies, resources, sequencing issues)
3. What assumptions or timelines look unrealistic -- and what evidence
   would confirm or refute them
4. What should change before proceeding

If domain-specific best practices matter, search for them and cite
what you find.

Do not rewrite the plan. Diagnose first.

End with a verdict: PROCEED or REVISE FIRST.

THE PLAN:
[paste here]
```

!!! tip "Use the strongest thinking model available"
    Heavier reasoning models produce sharper critique. Pick the most capable model available on your subscription -- the adversarial framing in this prompt does the rest.

---

## What to do with the output

**If the verdict is REVISE FIRST:** Address the "Must Fix" items. Then ask: *"Here is my revised plan addressing your concerns. Review it again."*

**If the verdict is PROCEED:** Scan the "Worth Considering" items. Decide consciously which risks you are accepting and which are worth a quick fix.

**For high-stakes plans** (briefs in complex litigation, clinic accreditation proposals, tenure materials): Open a second fresh chat with a modified role -- *"Review this plan as a [opposing counsel / accreditation reviewer / junior associate seeing this for the first time]."* Different personas catch different blind spots. For maximum independence, use separate conversations rather than asking for multiple personas in one chat.

---

## Common mistakes

**Reviewing in the same conversation where you built the plan.** The model will hedge its criticism because it participated in creation. Always use a fresh chat.

**Trusting the verdict without reading the findings.** The classification is a starting point. Read each finding and decide for yourself whether it applies to your situation. AI reviewers can be overconfident about risks that do not apply to your context ([ScienceDirect, 2025](https://www.sciencedirect.com/science/article/pii/S1071581925002149)).

**Using a plan that is too vague.** A 3-sentence sketch gets a 3-sentence review. Include concrete steps, timelines, resources, and constraints.

**Adopting the AI's revision wholesale.** When you ask for a revised plan, the model produces something plausible and polished. Resist adopting it without thinking. The revision is a starting point, not a replacement for your professional judgment ([PMC, 2023](https://pmc.ncbi.nlm.nih.gov/articles/PMC10546443/)).

---

## Save this for repeat use

If you review plans regularly, save the prompt as a persistent project instead of pasting it each time.

### Claude.ai Project

1. Go to [claude.ai/projects](https://claude.ai/projects) (requires Pro, Team, or Enterprise)
2. Click **"+ New Project"**
3. Name it **"Plan Reviewer"**
4. Click **"Set Custom Instructions"** and paste the prompt from above
5. Optionally upload reference documents (your firm's brief standards, past post-mortems, regulatory checklists)

To use: open the project, start a **new conversation** each time, paste your plan. The instructions apply automatically. Each new conversation gets fresh context -- no cross-contamination between reviews. ([Claude Help Center -- Projects](https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects))

### ChatGPT Custom GPT

1. Go to [chatgpt.com/create](https://chatgpt.com/create) (requires Plus, Team, or Enterprise)
2. Click the **Configure** tab
3. Set name: **Plan Reviewer**; paste the prompt into Instructions
4. Enable **Web Browsing**; disable DALL-E and Code Interpreter
5. Save and choose **"Anyone with a link"** to share with colleagues

To use: start a new conversation with the GPT each time. Colleagues can use it immediately via the shared link -- no setup on their end. ([OpenAI -- Creating a GPT](https://help.openai.com/en/articles/8554397-creating-a-gpt))

### Tips for both

- **Always start a new conversation** for each plan -- reusing an old conversation reintroduces the anchoring problem
- Keep a versioned copy of your instructions in a local text file with dates and change notes
- Test with one plan you know is solid and one you know has problems before sharing with colleagues

---

??? info "Sources and references"

    - [Extended Thinking -- Anthropic](https://www.anthropic.com/news/visible-extended-thinking) -- How extended thinking works in Claude models: deeper reasoning before responding, improving critical analysis.
    - [AI Personas Considered Harmful? -- ScienceDirect](https://www.sciencedirect.com/science/article/pii/S1071581925002149) -- Research on automation bias: users over-trust AI output, especially when it is well-formatted and confident.
    - [Mitigating Bias in AI -- PMC/NIH](https://pmc.ncbi.nlm.nih.gov/articles/PMC10546443/) -- AI bias patterns and the importance of human-in-the-loop validation.
    - [Prompting Best Practices -- Anthropic API Docs](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices) -- Calm, specific directives outperform aggressive language; give permission to express uncertainty.
    - [How Can I Create and Manage Projects? -- Claude Help Center](https://support.claude.com/en/articles/9519177-how-can-i-create-and-manage-projects) -- Creating Projects, setting custom instructions, sharing with teams.
    - [Creating a GPT -- OpenAI Help Center](https://help.openai.com/en/articles/8554397-creating-a-gpt) -- Building Custom GPTs: Configure tab, instructions, capabilities, publishing.

*Current as of April 2026. Model names and capabilities change frequently.*
