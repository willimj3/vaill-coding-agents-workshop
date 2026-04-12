# Privacy and Data Handling

*Last updated: April 2026*

Using AI tools in legal work raises serious data privacy questions. This page covers two things: (1) how this website handles your data, and (2) the privacy framework every law faculty member should understand before using AI tools with sensitive information.

---

## This Website

### Analytics

This site uses [GoatCounter](https://www.goatcounter.com), an open-source, privacy-friendly analytics tool. GoatCounter does not use cookies, does not track you across sites, and does not collect personal information. It counts page views so we know which guides are useful and which need work.

GoatCounter is free for non-commercial use and its code is fully open source. No data is shared with third parties. You can read their [privacy policy](https://www.goatcounter.com/help/privacy) for details.

### Your Rights

This is a static documentation site. We do not collect personal information beyond anonymous page view counts. There is nothing to delete because we do not store anything about you.

---

## AI Tools and Confidentiality: What Law Faculty Need to Know

This section is not legal advice. It is a practical framework for thinking about data privacy when using AI tools in legal work and legal education.

### The core question

Every time you paste text into an AI tool, you are sending data to a server. The question is: **what happens to that data?** The answer depends on which tool you are using and how you are using it.

### Consumer products vs. API access

This distinction matters more than most people realize.

| | Consumer product (browser chatbot) | API / Claude Code |
|---|---|---|
| **Examples** | claude.ai free tier, chatgpt.com free tier | Claude Code, API access via paid plans |
| **Training on your data** | May use conversations to improve models (varies by provider and plan) | Anthropic and OpenAI commit to **not training on API data** |
| **Data retention** | Conversations stored on provider servers, typically 30+ days | Typically shorter retention; varies by provider |
| **Best for** | General questions, non-sensitive work | Work involving any sensitive information |

!!! warning "Key point for legal professionals"
    If you are working with **any** client information, student records, or unpublished research, use API-based access (like Claude Code with a paid plan) rather than a free-tier consumer chatbot. The data handling commitments are meaningfully different.

### What stays local vs. what gets transmitted

When you use Claude Code:

- **Stays on your machine:** Your files, your CLAUDE.md configuration, your local project folders
- **Sent to Anthropic's servers:** The content of your prompts, any text you paste or ask Claude to read, and Claude's responses
- **Not sent:** Files Claude has not been asked to read; your broader filesystem

Claude Code does not silently upload your documents. It sends only the specific content involved in the current conversation. But that content *is* transmitted -- so you need to think about what you include.

---

## Legal-Specific Privacy Concerns

### Client confidentiality (ABA Model Rule 1.6)

[Model Rule 1.6](https://www.americanbar.org/groups/professional_responsibility/publications/model_rules_of_professional_conduct/rule_1_6_confidentiality_of_information/) requires lawyers to make "reasonable efforts to prevent the inadvertent or unauthorized disclosure of, or unauthorized access to, information relating to the representation of a client."

What this means for AI use:

- **Do not paste client-identifying information** into consumer AI tools without understanding the provider's data handling practices
- **Anonymize or redact** client names, case numbers, and identifying details before using AI for analysis
- **Review your engagement letters** -- some clients may have specific requirements about data handling that restrict AI tool use
- **Check your jurisdiction** -- several state bars have issued ethics opinions specifically addressing AI and confidentiality

### Student data (FERPA)

For law faculty, the Family Educational Rights and Privacy Act (FERPA) restricts how we handle student records. This applies to AI tools:

- **Do not paste student names, grades, or identifying information** into AI tools
- **Anonymize before analyzing** -- if you want AI help analyzing student performance patterns, remove identifying information first
- **Course evaluations and feedback** should be anonymized before any AI analysis
- **Check with your institution** -- your university likely has specific policies about AI and student data

### Unpublished research

If you are using AI to help with unpublished scholarship, working papers, or grant applications:

- **Your ideas are not protected by AI providers' terms of service.** Even if the provider does not train on your data, your prompts pass through their infrastructure.
- **For highly sensitive pre-publication work,** consider whether the efficiency gain justifies the (small but nonzero) risk
- **Patent-sensitive research** may have additional disclosure concerns -- consult your technology transfer office

---

## Institutional Policies

Your law school or university likely has (or is developing) policies on AI use. Before adopting any AI workflow for work involving institutional data:

1. **Check your institution's AI policy.** Many universities issued guidance in 2024-2025. Look for policies from the provost's office, IT department, or general counsel.
2. **Review your law school's specific guidance.** Some law schools have additional requirements beyond the university policy.
3. **Understand your IT department's position** on installing software like Claude Code on university-managed devices.
4. **Ask about enterprise agreements.** Your institution may have negotiated terms with AI providers that offer better data protections than individual subscriptions.

!!! tip "A practical approach"
    For most law faculty work -- drafting syllabi, outlining scholarship, preparing teaching materials, analyzing publicly available cases -- consumer AI tools with a paid subscription are fine. The privacy concerns become serious when you are working with client information, student records, or pre-publication research. When in doubt, anonymize first.

---

## Recommended Practices

| Scenario | Recommendation |
|----------|---------------|
| Drafting a syllabus or course materials | Any AI tool is fine -- this is not sensitive information |
| Analyzing published case law | Any AI tool is fine -- published opinions are public |
| Working with client information (clinic or consulting) | Use API-based tools; anonymize identifying details |
| Analyzing student performance data | Anonymize completely before any AI processing |
| Drafting unpublished scholarship | Paid subscription (API-level data protections); avoid pasting core novel arguments if concerned |
| Grant applications with proprietary methods | Consider risk tolerance; anonymize where possible |

---

## Further Reading

- [Anthropic Privacy Policy](https://www.anthropic.com/policies/privacy) -- How Anthropic handles data from Claude and Claude Code
- [OpenAI Privacy Policy](https://openai.com/policies/privacy-policy/) -- How OpenAI handles data from ChatGPT
- [ABA Formal Opinion 512 (2024)](https://www.americanbar.org/groups/professional_responsibility/publications/ethics_opinions/) -- Lawyers' obligations when using generative AI
- [FERPA Guidance (US Department of Education)](https://studentprivacy.ed.gov/) -- Federal requirements for student data protection

---

## Questions

If you have questions about data handling for the tools covered in this guide, contact the [Vanderbilt AI Law Lab](https://law.vanderbilt.edu/vanderbilt-ai-law-lab/).
