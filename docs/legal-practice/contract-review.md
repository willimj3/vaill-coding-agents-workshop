# Contract Review

<span class="badge-teal">Works in chatbots and Claude Code</span>

Contract review is one of the most immediately practical applications of AI in legal work. The task is well-defined, the domain knowledge is relatively stable, and the consequences of a missed clause are concrete enough that you know exactly what to verify.

This page covers how to use AI to review contracts for key clauses, non-standard terms, missing provisions, and potential risks -- and how to set up a reusable system for recurring contract types.

!!! warning "AI is a first-pass tool, not a final reviewer"

    AI can identify issues, flag unusual language, and compare terms against standard benchmarks. It cannot understand the business context, the relationship between the parties, or the strategic implications of a particular clause. You review the AI's work, not the other way around.

---

## What AI Does Well in Contract Review

AI is genuinely useful for:

- **Identifying standard clause types** -- indemnification, limitation of liability, termination, assignment, governing law, force majeure
- **Flagging non-standard language** -- terms that deviate from what is typical for the contract type
- **Spotting missing provisions** -- common clauses that are absent from the draft
- **Summarizing key terms** -- producing a structured term sheet from a full contract
- **Comparing versions** -- identifying differences between two drafts
- **Checking internal consistency** -- do defined terms match their usage throughout? Do cross-references point to the correct sections?

---

## A Basic Contract Review Prompt

Start with this and adapt it to your needs:

```text
You are a senior corporate attorney reviewing a contract for a client.

Review the attached [CONTRACT TYPE] and provide a structured analysis:

1. KEY TERMS SUMMARY
   - Parties, effective date, term, renewal provisions
   - Payment terms and financial obligations
   - Key performance obligations of each party

2. RISK ANALYSIS
   - Identify clauses that favor the counterparty
   - Flag any indemnification obligations that are unusually broad
   - Note limitation of liability provisions and any carve-outs
   - Identify representations and warranties that may be difficult to satisfy

3. NON-STANDARD TERMS
   - Flag language that deviates from standard [CONTRACT TYPE] terms
   - Note any unusual definitions
   - Identify provisions that are uncommon for this contract type

4. MISSING PROVISIONS
   - List standard provisions for this contract type that are absent
   - For each missing provision, explain why it matters

5. INTERNAL CONSISTENCY
   - Check that defined terms are used consistently
   - Verify cross-references
   - Note any ambiguities in key terms

Organize the output with headers for each section. For each issue
identified, rate its severity as HIGH, MEDIUM, or LOW and explain
your reasoning in one sentence.
```

=== "In a chatbot (Claude.ai or ChatGPT)"

    Paste the prompt above into a chat window, then paste or upload the contract text. For longer contracts, upload the PDF directly -- both Claude and ChatGPT handle PDF uploads well.

=== "In Claude Code"

    Save the contract to a local folder and point Claude Code at it:

    ```
    Review the NDA at ~/contracts/acme-nda-2025.pdf using our standard
    contract review protocol.
    ```

    If you have a CLAUDE.md configured for contract review (see below), Claude Code already knows your review protocol and preferences.

---

## Setting Up a CLAUDE.md for Contract Review

A CLAUDE.md file tells Claude Code about your practice, your preferences, and your standards -- before you even ask a question. For contract review, this is particularly valuable because it encodes jurisdiction-specific requirements, client preferences, and your firm's standard positions.

Here is a template. Adapt it to your practice:

```markdown
# Contract Review Configuration

## Practice Context
- Jurisdiction: [Your primary jurisdiction, e.g., "New York"]
- Client type: [e.g., "Mid-size technology companies, typically the receiving party"]
- Risk tolerance: [e.g., "Moderate -- client prefers balanced terms but
  will push back on unlimited indemnification"]

## Review Standards
- Always check for: governing law, dispute resolution mechanism,
  indemnification scope, limitation of liability, IP ownership,
  confidentiality obligations, termination rights, assignment restrictions
- Flag if missing: data protection provisions (CCPA/GDPR where applicable),
  force majeure, notice requirements, survival clauses
- Jurisdiction-specific: [e.g., "New York requires consideration for
  non-competes. Flag any restrictive covenants that lack consideration."]

## Output Preferences
- Use severity ratings: HIGH / MEDIUM / LOW
- For each issue, include: (1) the specific clause, (2) the concern,
  (3) suggested alternative language where appropriate
- Produce a one-page executive summary suitable for sending to the client
  in addition to the detailed analysis

## Recurring Contract Types
- NDAs: We use a standard mutual NDA. Flag any terms that deviate from
  mutual obligations. Key concerns: definition of confidential information,
  exclusions, term length, return/destruction obligations.
- SaaS agreements: Focus on SLA terms, data handling, uptime guarantees,
  and limitation of liability for data breaches.
- Employment agreements: Check restrictive covenants against [jurisdiction]
  enforceability standards.

## What I Will Always Verify Myself
- Business terms and pricing (AI does not know the deal)
- Strategic implications of non-standard terms
- Whether flagged issues are actually problems given the relationship context
- Jurisdiction-specific enforceability of restrictive covenants
```

Save this as `CLAUDE.md` in your contracts project folder. Claude Code reads it automatically at the start of every session in that folder.

---

## An AI Project Folder for Contract Review

For recurring contract types, set up a dedicated project folder:

```
contracts/
  CLAUDE.md                    # Review configuration (above)
  templates/
    standard-nda.md            # Your firm's standard NDA terms
    standard-saas.md           # Your standard SaaS agreement terms
    clause-library.md          # Preferred language for common clauses
  active/
    acme-nda-2025.pdf          # Current contracts under review
    globex-saas-draft-3.pdf
  completed/
    [Move completed reviews here]
```

The `templates/` folder is the key. When you tell Claude Code to review a new NDA, it can compare the incoming draft against your standard terms and tell you exactly where the counterparty's draft deviates. That comparison is far more useful than a generic "this clause is non-standard" flag.

---

## Example: Reviewing an NDA

Here is a practical example of reviewing a non-disclosure agreement. The prompt assumes you have a CLAUDE.md configured as above.

```text
Review the NDA at active/acme-nda-2025.pdf.

Compare it against our standard NDA template in templates/standard-nda.md.

For each deviation from our standard:
1. Quote the relevant language from both documents
2. Explain the practical impact of the deviation
3. Rate the severity (HIGH/MEDIUM/LOW)
4. Suggest specific redline language if we should push back

Also check for:
- Any provisions that are missing from the Acme draft that our
  standard includes
- Internal consistency issues
- Ambiguities in the definition of Confidential Information

Produce two outputs:
1. A detailed analysis (for my file)
2. A one-paragraph email summary I can send to the client highlighting
   the 3-5 most important issues
```

This prompt works because it gives Claude Code a specific reference point (your standard template) rather than asking it to evaluate the contract against some abstract notion of "standard." Comparison is where AI shines.

---

## Limitations You Must Understand

AI contract review has specific failure modes that you need to know about:

| Limitation | Why It Matters | Your Mitigation |
|-----------|---------------|-----------------|
| **Jurisdiction-specific rules** | AI may not know that your jurisdiction treats a particular clause differently | Always verify enforceability of key provisions in your jurisdiction |
| **Novel provisions** | AI benchmarks against what it has seen in training data; truly novel provisions may not be flagged | Read every clause yourself; use AI for speed, not as a substitute for reading |
| **Business context** | AI does not know the deal, the relationship, or the negotiation dynamics | AI tells you what a clause *says*; you decide what it *means* for this client |
| **Implied terms** | Some jurisdictions imply terms into certain contract types; AI may not account for these | Know the implied terms for your contract types in your jurisdiction |
| **Recent law changes** | AI training data has a cutoff date; recent legislation or case law may not be reflected | Verify any regulatory compliance issues against current law |
| **Strategic implications** | A clause that looks problematic in isolation may be acceptable as part of a negotiated package | Apply your negotiation judgment to every AI recommendation |

---

## The Always-Verify Checklist

Before relying on any AI contract review, verify the following yourself:

- [ ] **Read the entire contract.** AI review is a supplement, not a substitute for reading. Skim at minimum; read closely any sections the AI flagged.
- [ ] **Check governing law.** Confirm the AI's analysis is consistent with the governing jurisdiction. AI may default to general U.S. law when your contract is governed by a specific state's law.
- [ ] **Verify defined terms.** Confirm that the AI correctly identified how key terms are defined and that its analysis uses the contract's definitions, not general meanings.
- [ ] **Validate the "missing provisions" list.** Some provisions the AI flags as "missing" may be intentionally omitted or covered elsewhere. Check against the business context.
- [ ] **Test internal cross-references.** If the AI flagged cross-reference issues, verify them manually. If it did not flag any, spot-check a few yourself.
- [ ] **Review suggested language.** AI-generated redline suggestions may be legally sound in general but inappropriate for your specific negotiation context. Edit before sending.
- [ ] **Confirm regulatory compliance.** For contracts involving regulated industries, data protection, or specific statutory requirements, verify compliance against current regulations, not the AI's training data.

---

## Ethics Considerations for AI-Assisted Contract Review

!!! danger "ABA Model Rule 1.1: Competence"

    Using AI for contract review is consistent with the duty of competence -- provided you understand the tool's limitations and verify its output. The risk arises when a lawyer relies on AI review without independent verification. The standard is the same as it would be for work delegated to a junior associate: you must review it with the care of a competent practitioner.

**Confidentiality.** If you are pasting contract text into a consumer chatbot (ChatGPT, Claude.ai), the text may be processed on remote servers. For sensitive transactions:

- Use Claude Code with local files (the contract stays on your machine)
- Review your AI provider's data handling policies
- Consider whether the contract itself contains a confidentiality provision that restricts sharing its contents with third-party services
- Redact party names and identifying details if using a consumer chatbot for general clause analysis

**Billing.** AI can dramatically reduce the time required for contract review. Be transparent with clients about your use of AI tools and adjust billing accordingly. Some jurisdictions and bar associations have issued guidance on this; check your local rules.

**Unauthorized practice.** If you are using AI to review contracts in a jurisdiction where you are not licensed, the analysis does not constitute legal advice. This matters most for multi-jurisdictional transactions. AI can flag issues, but the legal judgment about those issues must come from a lawyer licensed in the relevant jurisdiction.

---

## Next Steps

<div class="grid cards" markdown>

-   **Set up your contract review folder**

    ---

    Create the folder structure described above. Start with one contract type you review frequently. Build out from there.

-   **Build your clause library**

    ---

    Start collecting your preferred language for common clauses in a `clause-library.md` file. AI can compare incoming drafts against this library and suggest your standard language as redlines.

-   **Try the NDA example**

    ---

    Take an NDA you reviewed recently and run it through the prompt above. Compare the AI's output to your own review. Note where it caught things you might have missed, and where it missed things you caught.

</div>

---

## Related Pages

- [Teaching AI Your Voice](../essentials/voice.md) -- Create a voice file for your legal writing style
- [AI Project Folders](../essentials/project-folders.md) -- The general framework for project folder setup
- [Your CLAUDE.md](../toolkit/claude-md.md) -- How to configure Claude Code's persistent instructions
