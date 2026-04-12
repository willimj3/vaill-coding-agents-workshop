# Client Communication

<span class="badge-teal">Works in chatbots and Claude Code</span>

Clear client communication is as important as the underlying legal work. A brilliant analysis is worthless if the client cannot understand it, and a routine status update that arrives late -- or never -- erodes trust faster than any legal setback.

AI can help with the mechanical parts of client communication: drafting letters, translating legal concepts into plain language, maintaining consistent tone across a high volume of correspondence. But client communication also involves confidential information, which means the tools you use and how you use them matter as much as the quality of the output.

!!! danger "The cardinal rule of AI and client communication"

    **Never paste client-identifiable information into a consumer AI product unless you have reviewed the provider's data handling policies and determined that doing so is consistent with your confidentiality obligations.** This includes names, case details, financial information, and any other information that could identify the client or the matter. When in doubt, use Claude Code with local files or redact identifying details before using a chatbot.

---

## What AI Does Well in Client Communication

AI is useful for:

- **Drafting routine correspondence** -- status updates, scheduling letters, document transmittals, and other standard communications
- **Translating legal concepts** -- converting technical legal analysis into language a non-lawyer client can understand
- **Maintaining consistent tone** -- using a voice file ensures all communications from your office sound professional and consistent
- **Drafting engagement letters** -- producing first drafts of engagement letters with standard terms
- **Suggesting structure** -- organizing complex client updates so the most important information comes first
- **Proofreading and tone-checking** -- catching errors and ensuring the tone is appropriate for the audience

---

## A Voice File for Client Communication

Legal writing for a court audience is formal, citation-heavy, and technical. Client communication is different. Clients need clarity, warmth, and directness -- without jargon.

Create a separate voice file for client-facing writing:

```markdown
# Client Communication Voice

## Audience
- Non-lawyer clients who are intelligent but unfamiliar with legal
  terminology
- Busy professionals who want to know what is happening, what it
  means, and what they need to do

## Tone
- Professional but warm. Not stiff, not casual.
- Confident and reassuring. Clients are often anxious; your tone
  should project competence and control.
- Direct. Lead with the news, then explain. Do not bury the key
  information in paragraph three.

## Structure Rules
- First sentence: What happened or what is the purpose of this letter
- Second paragraph: What it means for the client
- Third paragraph: What the client needs to do (if anything)
- Close: Next steps and how to reach you
- Maximum one page for routine updates. If it is longer, add a
  summary at the top.

## Language Rules
- Define any legal term the first time you use it. Example:
  "The other side filed a motion to dismiss (a request asking the
  court to throw out the case)."
- No Latin without a translation.
- No citations in client letters (save those for the brief).
- Short sentences. Average 15 words. Maximum 25.
- Active voice. "We filed the motion" not "the motion was filed."

## Vocabulary
- "The other side" not "opposing counsel" or "the defendant"
- "The judge" not "the Court"
- "Agreement" not "contract" (for most client audiences)
- "Deadline" not "statute of limitations" (explain the concept instead)
- Avoid: "pursuant to," "hereinafter," "the aforementioned,"
  "please be advised that"

## Ban List (AI defaults to avoid)
- "I hope this email finds you well" (say nothing or say something
  real)
- "Please do not hesitate to contact me" (just say "call me anytime")
- "Delve," "navigate," "robust," "multifaceted"
```

Load this voice file into a Claude.ai Project for client communication, or save it in your CLAUDE.md for a Claude Code project dedicated to client correspondence.

---

## Common Client Communication Templates

### Status Update

```text
Draft a client status update letter using the following information:

Client: [Name -- or use "the client" if working in a consumer chatbot]
Matter: [General description]
Recent developments:
- [Development 1]
- [Development 2]
Next steps:
- [Next step 1 with timeline]
- [Next step 2 with timeline]
Action needed from client: [Yes/No -- if yes, what specifically]

Use a warm, professional tone. No legal jargon. Keep it to one page.
Lead with the most important development. Close with next steps and
how to reach me.
```

### Engagement Letter

```text
Draft an engagement letter for the following representation:

Type of matter: [e.g., contract negotiation, litigation, estate planning]
Scope of representation: [What we will and will not do]
Fee arrangement: [Hourly / flat fee / contingency -- with details]
Estimated timeline: [If applicable]
Key terms to include:
- Billing practices (when invoices are sent, payment terms)
- Communication expectations (how often we will update the client)
- File retention policy
- Termination provisions

Use formal but accessible language. The client should understand
every term without a law degree. Include placeholders for [FIRM NAME],
[CLIENT NAME], and [DATE] so I can fill them in.
```

### Adverse Development Notification

Communicating bad news requires particular care. AI can help you structure the communication, but the empathy and judgment about timing and delivery are yours.

```text
Draft a letter informing the client about an adverse development:

Development: [What happened]
Impact on the case: [What it means practically]
Our assessment: [How serious this is, in honest terms]
Our plan: [What we will do in response]
What the client should expect next: [Timeline, next steps]

Tone: Honest, calm, and confident. Do not minimize the setback, but
convey that we have a plan. The client should feel informed, not
alarmed. Lead with what happened, then immediately move to our response.

Do not use phrases like "unfortunately" or "I regret to inform you"
more than once. State the facts directly.
```

---

## Confidentiality: Choosing the Right Tool

The choice of AI tool matters for client communication because you are working with confidential information. Here is a decision framework:

| Scenario | Recommended Tool | Why |
|----------|-----------------|-----|
| **Drafting a template** (no client details) | Any chatbot | No confidential information involved |
| **Drafting with client details** | Claude Code with local files | Information stays on your machine |
| **Quick tone-check on a draft** | Chatbot with details redacted | Replace names and specifics with placeholders before pasting |
| **Bulk client correspondence** | Claude Code with local files | Process multiple letters without uploading client data to a cloud service |
| **Email triage and response drafting** | Claude Code with MCP (Gmail) | See note below on MCP email access |

### Using Claude Code with Local Files for Sensitive Work

Claude Code processes files on your local machine. When you ask it to draft a client letter, the information does not leave your computer unless you explicitly send it somewhere. This makes it the preferred tool for any client communication that involves confidential details.

```text
Read the case summary at ~/cases/smith-matter/case-summary.md and
draft a status update letter to the client covering the developments
from the past two weeks. Use our standard client communication
voice file.
```

The case summary stays on your machine. The AI reads it locally, drafts the letter locally, and the output stays local until you choose to send it.

### Email Triage and Response Drafting with MCP

If you have configured MCP connections (see [MCP Connections](../toolkit/mcp-setup.md)), Claude Code can access your email directly and help with:

- **Triage.** "Show me all emails from clients this week that need a response, sorted by urgency."
- **Response drafting.** "Draft a response to the email from [client] about the upcoming deposition. Confirm the date and remind them to bring the documents we discussed."
- **Follow-up tracking.** "Which client emails from last week have I not responded to?"

!!! warning "MCP email access and confidentiality"

    When Claude Code accesses your email through MCP, it reads the email content locally. The content is sent to Claude's API for processing, which means it does leave your machine. Review Anthropic's data handling policies and your firm's data governance requirements before using this feature for client communications. Consider whether your engagement letters permit the use of AI tools for client correspondence.

---

## An AI Project Folder for Client Communication

Set up a dedicated folder for recurring client communications:

```
client-communications/
  CLAUDE.md                     # Client communication configuration
  voice/
    client-voice.md             # Voice file for client-facing writing
  templates/
    status-update.md            # Status update template
    engagement-letter.md        # Engagement letter template
    adverse-development.md      # Bad news letter template
    closing-letter.md           # Matter closing letter template
    fee-estimate.md             # Fee estimate letter template
  active/
    [Current drafts]
  sent/
    [Archive of sent communications]
```

### A CLAUDE.md for Client Communication

```markdown
# Client Communication Configuration

## Practice Context
- Firm: [Firm name]
- My role: [Partner / Associate / title]
- Primary practice area: [e.g., commercial litigation, corporate, family law]
- Typical client: [e.g., small business owners, individuals, corporate executives]

## Communication Standards
- All client letters should be warm, professional, and jargon-free
- Load voice/client-voice.md for every drafting task
- Maximum one page for routine updates
- Use templates from templates/ as starting points when available
- Always include: next steps, timeline, and how to reach me

## Confidentiality Protocol
- Never use client names in prompts to external chatbots
- Use Claude Code with local files for any communication involving
  client details
- When drafting templates (no client details), any tool is acceptable
- If I paste an email thread, assume it is confidential and handle
  accordingly

## What I Will Always Write Myself
- The opening line of bad news letters (tone is critical)
- Fee discussions and billing disputes
- Communications involving settlement negotiations
- Any communication where the client has expressed emotional distress
```

---

## Practical Tips

**Batch your drafting.** If you have five client updates to send, draft them all in one Claude Code session. The AI maintains context about your voice and style across the session, so the fifth letter will be as consistent as the first.

**Read every draft aloud.** Client letters should sound like you talking to the client. If a sentence sounds like it was written by a machine, rewrite it. Reading aloud catches AI-isms that your eye skips over on screen.

**Maintain a "sent" archive.** Keep copies of sent communications in your project folder. Over time, this becomes a corpus that AI can learn from -- "Draft a letter similar to the one I sent to [previous client] about [similar situation]."

**Adapt templates, do not use them verbatim.** AI templates are starting points. Every client is different, every situation has nuances, and every letter should feel like it was written for this specific person about this specific matter.

**Use AI for the second draft, not just the first.** After you revise an AI draft, paste your revision back and ask: "Does this read clearly to a non-lawyer? Are there any terms that need further explanation? Is the tone consistent throughout?"

---

## Ethics Considerations for AI-Assisted Client Communication

!!! danger "Model Rule 1.6: Confidentiality"

    The duty of confidentiality applies to all information relating to the representation. Pasting client information into a consumer AI product may constitute a disclosure that violates Rule 1.6, depending on the AI provider's data handling policies. Use local tools for sensitive work. When in doubt, redact identifying details.

**Informed consent.** Consider whether to inform clients that you use AI tools in your practice. Some bar associations have suggested that the use of AI tools should be disclosed to clients, particularly where the AI has access to client information. Even where disclosure is not required, transparency builds trust.

**Unauthorized practice.** AI-drafted client communications go out under your name and your bar license. You are responsible for every word. Review every letter before sending it with the same care you would give to a letter drafted by a paralegal or junior associate.

**Billing.** If AI reduces the time required to draft client communications, your billing should reflect that. Charging an hour for a letter that AI drafted in five minutes and you reviewed in ten raises ethical concerns under Model Rule 1.5 (fees).

**Accessibility.** AI can help you communicate with clients who have different levels of legal sophistication. Use this capability to make your communications more accessible, not less. A client letter that requires a law degree to understand has failed its purpose regardless of who or what drafted it.

---

## Next Steps

<div class="grid cards" markdown>

-   **Create your client voice file**

    ---

    Adapt the template above with examples from your own client correspondence. The voice file is the single most impactful thing you can do for consistent, high-quality client communication.

    [:octicons-arrow-right-24: Teaching AI Your Voice](../essentials/voice.md)

-   **Set up your communication folder**

    ---

    Create the project folder structure above. Start with two or three templates for your most common communications.

-   **Review your confidentiality protocols**

    ---

    Before using any AI tool for client communication, review your firm's data governance policies and your AI provider's terms of service. Establish clear rules for yourself about what information goes where.

</div>

---

## Related Pages

- [Contract Review](contract-review.md) -- AI-assisted review of client contracts
- [Teaching AI Your Voice](../essentials/voice.md) -- The general voice file framework
- [MCP Connections](../toolkit/mcp-setup.md) -- Setting up email and file access for Claude Code
