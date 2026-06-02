# Privacy and Data Handling

*This page reflects the current state of these tools at time of publication. AI vendors update privacy practices frequently — verify the linked policies before relying on any specific detail.*

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

### Consumer accounts vs. commercial accounts

This distinction matters more than most people realize. It is not enough to ask whether the tool is "paid." A paid individual subscription and a commercial, API, Team, Enterprise, Edu, or institutionally managed account can have different data terms.

| | Individual consumer accounts | Commercial, API, or institutionally managed accounts |
|---|---|---|
| **Examples** | Claude Free/Pro/Max; ChatGPT Free/Plus/Pro | Claude Team/Enterprise/API; ChatGPT Business/Enterprise/Edu/API |
| **Training on your data** | May depend on your data controls, account settings, feedback choices, and safety-review exceptions | Providers generally commit not to use customer inputs/outputs to train models unless the customer opts in |
| **Data retention** | Varies by provider, product, and settings | Usually governed by commercial terms; may offer shorter retention or additional controls |
| **Best for** | General questions and non-sensitive work | Sensitive work, if approved by your institution and consistent with client/student obligations |

!!! warning "Key point for legal professionals"
    If you are working with **client information, student records, or unpublished research**, do not rely on the fact that a tool is paid or local-looking. Check the specific account type, data controls, institutional approvals, and governing terms. For high-sensitivity work, commercial/API/institutionally approved tools are usually safer than individual consumer subscriptions, but they are not a substitute for professional judgment.

### What stays local vs. what gets transmitted

When you use Claude Code:

- **Stays on your machine unless needed for the task:** Your broader filesystem, files Claude has not been asked to read, and your local project folders
- **Sent to Anthropic's servers:** Your prompts, Claude's responses, and the text or file excerpts Claude reads to complete the task
- **Stored locally:** Claude Code also stores local session data so you can resume conversations

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
| Working with client information (clinic or consulting) | Use only institutionally approved commercial/API tools; anonymize identifying details where possible |
| Analyzing student performance data | Anonymize completely before any AI processing |
| Drafting unpublished scholarship | Use a paid or institutional tool with appropriate data settings; avoid pasting core novel arguments if concerned |
| Grant applications with proprietary methods | Consider risk tolerance; anonymize where possible |

---

## Further Reading

- [Claude Code Data Usage](https://code.claude.com/docs/en/data-usage) -- How Anthropic describes Claude Code data flow, training, and retention
- [Anthropic Privacy Policy](https://www.anthropic.com/policies/privacy) -- Anthropic's general privacy policy
- [OpenAI Privacy Policy](https://openai.com/policies/privacy-policy/) -- How OpenAI handles data from ChatGPT
- [ABA Formal Opinion 512 (2024)](https://www.americanbar.org/content/dam/aba/administrative/professional_responsibility/ethics-opinions/aba-formal-opinion-512.pdf) -- Lawyers' obligations when using generative AI
- [FERPA Guidance (US Department of Education)](https://studentprivacy.ed.gov/) -- Federal requirements for student data protection

---

## Questions

If you have questions about data handling for the tools covered in this guide, contact the [Vanderbilt AI Law Lab](https://law.vanderbilt.edu/vanderbilt-ai-law-lab/).
