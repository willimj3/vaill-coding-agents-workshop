# School Email Digest: Raw Materials for Blog Post
*Compiled March 3, 2026 — Source material for claudeblattman.com*

This document contains excruciating detail about the development of the `/school-digest` skill. It is NOT a blog post — it is raw material for Claude Blattman to later construct a page. Everything here is factual, drawn from the actual development session transcript.

---

## 1. THE PROBLEM

Chris and Jeannie Blattman have two children in school:
- **Amara** — Wolcott College Prep, 9th grade (freshman)
- **Callum** — UChicago Lab School (Middle School), 7th grade

Both schools generate a high volume of email. Wolcott sends weekly newsletters via Constant Contact, event announcements, enrollment paperwork, fundraiser invitations, and direct teacher emails. UChicago Lab School sends daily Schoology bulletins (platform notifications), eNotice blasts from the principal/director/board, teacher emails, and its own fundraiser appeals.

### Chris's exact words about the problem:
> "I think it's useful to give the context of wondering why we get these ridiculously lengthy, detailed emails from our school, and so many of them, and the ease of missing really important deadlines or events or permission forms. How previously I was just having school emails skip the inbox and go into a special folder so I could review them as a batch every day or two, but even then some were pages long."

### The previous workflow:
Chris had already set up Gmail infrastructure to automatically label school emails with `@School` and remove them from his inbox. His existing AI triage system (`/checkin` and `/morning-brief` skills) would mark these as read during their regular sweeps. Chris would then batch-review the @School folder every day or two. But even with batching:
- Some newsletters were pages long (Wolcott's weekly newsletter, Lab School's daily bulletins)
- Important deadlines and permission forms got buried in noise
- Fundraiser appeals, enrollment confirmations, and marketing emails cluttered the folder
- A science test date or permission form due date could easily be missed

### From the plan document:
> "Chris and Jeannie receive several emails daily from their children's schools (Wolcott College Prep for Amara, UChicago Lab School for Callum). Important information — schedule changes, deadlines, permission slips — gets buried in long newsletters."

### The volume:
In the first live run, the skill processed **49 emails across 44 threads** covering just a 14-day window (Feb 17 – Mar 3, 2026). That's roughly 3.5 emails per day, every day, from two schools.

---

## 2. THE IDEA

Build a skill that:
1. Reads all `@School` emails since the last digest
2. Classifies each by urgency (HIGH / MEDIUM / LOW / SKIP)
3. Groups by child (Amara / Callum)
4. Compresses everything into a short, scannable digest
5. Emails it to Chris and Jeannie automatically every 2-3 days

The digest would go from `claudeblattman@gmail.com` (Chris's AI assistant identity) to both `blattman@gmail.com` and `jeannie.annan@gmail.com`.

### Key design constraint:
The skill queries by **date range**, not by unread status. This is because the existing triage infrastructure already marks @School emails as read. Deduplication uses a state file with message IDs to avoid re-processing.

---

## 3. THE CALIBRATION PROCESS

### Setting up: Three open questions

Before pulling any emails, Claude asked Chris three questions:

1. **Jeannie's consent:** "Does Jeannie know she'll receive digests from claudeblattman@gmail.com? Should we start Chris-only for the first couple runs?"
2. **Jeannie's inbox:** "Does Jeannie independently receive school emails in her own inbox?"
3. **Schoology handling:** "Schoology/eNotice platform notifications — include as FYI/Low or exclude entirely?"

**Chris's answers:**
- Q1: "Include Jeannie now"
- Q2: "Yes, she gets them too"
- Q3: "Let's wait and see, depending on what the content is. In addition, there may be other school-related materials related to alerts from school computer use, such as security or IT, etc."

### First calibration round: 20 emails

The first step was pulling 20 recent @School emails and having Chris rate each one. This happened at approximately 01:33 UTC on March 4, 2026.

**Key discovery during this phase:** The original plan assumed Schoology emails had content behind a login wall and should be summarized as "New item(s) in [child]'s Schoology — check app." In reality, **Schoology emails include full content inline**. This changed the entire approach to Schoology handling.

Here is the exact calibration table presented to Chris:

| # | Date | Child | Sender / Platform | Subject Summary | Claude's Rating |
|---|------|-------|-------------------|-----------------|-----------------|
| 1 | Mar 3 | Amara | Wolcott / Constant Contact | Grandparents Day Mon Mar 9, 1:30pm — registration required | Medium |
| 2 | Mar 3 | Callum | Schoology daily bulletin | 8th grade graduation auditions (form due Apr 7), DC T-shirt contest (due Fri), Callum's birthday Mar 7 listed, Emma Tsai farewell | Low |
| 3 | Mar 3 | Callum | Lab eNotice (Director) | 2026-27 tuition up 4.75% — MS: $47,106 | High |
| 4 | Mar 3 | Callum | Schoology (Emma Tsai) | Staff departure announcement, absence reporting reminders | Low |
| 5 | Mar 3 | Callum | Schoology daily bulletin | Duplicate of #2 (Tue edition), Bunco, yearbook surveys | Skip |
| 6 | Mar 3 | Amara | Wolcott Tyree Institute | College admissions event Wed Mar 18, 6:30pm. Juniors encouraged. | Medium |
| 7 | Mar 2 | Amara | Wolcott PA | PA meeting Fri Mar 6, 9am. 10th-grade parent social. Teacher appreciation breakfast donation. | Medium |
| 8 | Feb 28 | Amara | Wolcott | Benefit dinner / fundraiser — ticket purchase, auction | Skip |
| 9 | Feb 27 | Callum | Lab eNotice (Principal) | Parent-to-Parent meeting Tue Mar 3. Book drive. Save-the-dates: 7th camp May 19-22, 8th grade graduation June 9 | Medium |
| 10 | Feb 27 | Callum | Schoology (Abbey Cullen) | "Digital copy of info you received today" — link only, no content | Low |
| 11 | Feb 27 | Callum | Teacher (Schmidt) | Advisory conference Feb 27 confirmed — already happened | Skip |
| 12 | Feb 27 | Amara | Wolcott Business Office | Enrollment agreement signed by school — confirmation | Low |
| 13 | Feb 27 | Amara | Wolcott Business Office | All enrollment signatures complete — confirmation | Low |
| 14 | Feb 27 | Callum | Lab eNotice (Board Chair) | Director of Schools search launched, parent survey | Low |
| 15 | Feb 26 | Callum | Schoology | "Please complete Google Form" — link only, no context | Low |
| 16 | Feb 26 | Callum | Schoology daily bulletin | Unblocked schedule Thu, Caudill voting, music festival results | Low |
| 17 | Feb 26 | Callum | Teacher (Glinton) direct | Unit 5 science test Fri Mar 6. Study guide sent home. | High |
| 18 | Feb 26 | Amara | Wolcott weekly newsletter | Long roundup: summer enrichment, college counseling Mar 4, High School Musical Mar 11, Q3 ends Mar 20, spring break Mar 23-27 | Medium |
| 19 | Feb 26 | Callum | Schoology daily bulletin | MathCOUNTS results, journalism showcase, unblocked schedule | Low |
| 20 | Feb 25 | Callum | Schoology daily bulletin | No new announcements. MathCOUNTS chapter results. | Skip |

### Chris's first corrections

Chris's exact words (dictated via Wispr Flow):
> "1. One is low. 2. Two is low. 3. Three is high. 4. Four is low. 5. Five, skip. 6. Six, medium. 7. Seven, low. 8. Eight, skip. 9. Nine, low. 10. Ten, low. 11. Eleven, skip. 12. Twelve, skip. 13. Thirteen, skip. 14. Fourteen, low. 15. Fifteen depends if it's a permission form or something else that's necessary for Calm to participate in an activity or Amara to participate in an activity; it's high. 16. Sixteen, low. 17. Seventeen, high. 18. Eighteen, medium, mostly about the musical if it hasn't already been highlighted before. 19. Nineteen, low. 20. Twenty Add that to your patterns. Why don't you sample 30 random emails over the past six months so that we get a wider distribution?"

**Summary of where Claude and Chris disagreed:**

| # | Email | Claude Said | Chris Said | What This Teaches |
|---|-------|------------|------------|-------------------|
| 1 | Grandparents Day (registration required) | Medium | **Low** | Events/meetings are low unless parent action is needed for the child |
| 7 | PA Meeting + parent social | Medium | **Low** | Same principle — parent-focused events are low |
| 9 | Principal updates + camp dates | Medium | **Low** | Institutional updates are low, even with future dates embedded |
| 12 | Enrollment agreement signed | Low | **Skip** | Confirmations of completed actions → Skip |
| 13 | Enrollment signatures complete | Low | **Skip** | Same — admin confirmations → Skip |
| 15 | "Please complete Google Form" (link only) | Low | **High** | "Depends if it's a permission form or something else that's necessary" — short/link-only Schoology posts could be permission forms |
| 20 | Empty bulletin | Skip | **Skip + add to patterns** | Chris wanted systematic rules, not one-off decisions |

**Claude's observation after the first round:**
> "Your rankings shift the baseline lower than my defaults — most school comms are Low unless they require parent action or affect the kids directly."

### Second calibration round: 30 additional emails

Chris requested a wider sample: "Why don't you sample 30 random emails over the past six months so that we get a wider distribution?"

30 additional emails were pulled from Sep 2025 through Feb 2026:

| # | Date | Child | Type | Summary | Rating |
|---|------|-------|------|---------|--------|
| 21 | Oct 31 | Callum | Thread: nanny + teacher | Fwd of Glinton Unit 2 test to nanny re Callum's study plan | High (test) |
| 22 | Oct 31 | Callum | Same thread | Chris's fwd to nanny | Skip (own sent) |
| 23 | Oct 30 | Callum | Schoology bulletin | Q2 starts, Picture Day retakes, ceramics/dance registration | Low |
| 24 | Oct 30 | Amara | Wolcott weekly newsletter | Q1 ends, Fall sports banquet, Homecoming recap, college counseling event | Low |
| 25 | Oct 30 | Callum | Teacher (Neater) direct | Art project saving issue — resolved, Callum should submit self-assessment | High (teacher direct) |
| 26 | Oct 30 | Callum | Schoology | Parent-to-Parent recording on digital safety | Low |
| 27-29 | Oct 29-30 | Callum | Same art thread | Chris/Sunny earlier messages | Skip (thread dupes) |
| 30 | Oct 29 | Callum | Lab eNotice | Picture Day retakes Nov 4 | Low |
| 31 | Dec 31 | Callum | Lab eNotice | Last Day for 2025 Giving — donate now | Skip (fundraiser) |
| 32 | Dec 30 | Amara | Wolcott | College Knowledge for 9th/10th graders, Jan 7 | Low |
| 33 | Dec 30 | Callum | Lab eNotice | One Day Left of Giving Season | Skip (fundraiser) |
| 34 | Dec 24 | Amara | Stuart-Rodgers Photography | 20% off Amara's portraits | Skip (marketing) |
| 35 | Dec 23 | Callum | Lab eNotice | Wishing You Peace from ARD — donate | Skip (fundraiser) |
| 36 | Dec 22 | Amara | Wolcott | College Knowledge (duplicate of #32) | Skip (dupe) |
| 37 | Dec 20 | Amara | Wolcott counselor (Onyezia) direct | Re: Amara's social adjustment, Spanish class issue, phone policy | High (counselor direct) |
| 38 | Dec 19 | Callum | Lab eNotice (Director) | Winter break holiday greeting | Low |
| 39 | Dec 19 | Callum | Schoology | Found bag at L&C | Skip (lost & found) |
| 40 | — | Callum | Lab eNotice Athletics | Maroon Madness basketball event Jan 23 | Low |
| 41 | Feb 24 | Callum | Lab eNotice | Summer Lab registration — filling up | Low |
| 42 | Feb 24 | Amara | Wolcott | High School Musical March 11 | Low |
| 43 | Feb 24 | Amara | Wolcott Business Office | Enrollment signature received (Jeannie) | Skip (confirmation) |
| 44 | Feb 24 | Amara | Wolcott Business Office | Enrollment signature received (Chris) | Skip (confirmation) |
| 45 | Feb 23 | Amara | Wolcott Admissions (Spiro) | IMPORTANT: Revised enrollment agreements due Thu 2/26 at 5pm | High (deadline) |
| 46 | Feb 23 | Callum | Schoology bulletin | MathCOUNTS results, unblocked schedule, club cancellations | Low |
| 47 | Feb 23 | Amara | Wolcott (Head of School) | College counseling leadership transition | Low |
| 48 | Feb 23 | Amara | Wolcott Business Office | Enrollment Agreement — signature required | High (action required) |
| 49 | Feb 23 | Amara | Wolcott Business Office | Previous contract voided | Low (FYI) |
| 50 | Feb 23 | Amara | Wolcott Learning Specialist (Bomher) | Check-in re scheduling a call about Amara's progress | High (teacher direct) |

### Chris's second corrections

Chris's exact words (note: first sentence is a Wispr Flow dictation artifact — speech-to-text occasionally captures ambient audio or a misfire):
> "I'm so happy to be a part of your journey and to be a part of your life as well. Number 32, which is college knowledge for Amara's grade, which is ninth, is medium or high depending on the circumstances. We definitely want to engage in any video calls or other things. A high school musical announcement would be medium. Any high school dance or high school event for Amara or for the family would be medium. A leadership transition for a major post or for a counselor, like number 47, might be medium, might be low depending on the circumstances. Otherwise, your patterns are well done. Why don't you do that and then walk me through why we would do a dry run now if all of the messages are read? Also, will the email to Chris and Jeannie be automatically generated, or will I have to manually send it? I'd prefer it to be automatically sent."

**Key new rules from this feedback:**
- **College counseling events for Amara's grade** (9th) → Medium or High ("We definitely want to engage in any video calls or other things")
- **School performances** (High School Musical, etc.) → Medium
- **School social events** for Amara or family (dances, homecoming) → Medium
- **Leadership transitions** → Context-dependent, Medium or Low
- **Auto-send preference** → "I'd prefer it to be automatically sent"

### The auto-send decision

When Chris said he wanted auto-send, the skill was changed from "per-item confirm" (requiring Chris to approve each send) to "auto" risk tier. This was documented as a policy exception in the risk escalation rules, following the same pattern as the morning briefing auto-send:

> "Email send: **Auto** (policy exception: digest is a self-email to Chris + Jeannie from claudeblattman, not outbound to strangers. Auto-send approved by Chris on 2026-03-03.)"

---

## 4. THE RULES THAT EMERGED

Based on the 50-email calibration, these classification rules were seeded:

### HIGH — Action required
- Direct teacher/counselor emails (from personal addresses, not `noreply@`)
- Keywords: `signature required`, `enrollment agreement`, `IMPORTANT`, `deadline`, `due by`, `payment due`, `permission`, `consent form`, `health alert`, `emergency`
- Schedule disruptions: `early dismissal`, `school closing`, `schedule change`, `delayed start`
- Schoology link-only posts (could be permission forms)

### MEDIUM — Worth knowing
- School performances (musicals, plays)
- School social events for the children or family
- College counseling events for Amara's current grade
- Report cards, progress reports
- Field trips requiring RSVP

### LOW — FYI only
- Schoology daily bulletins (unless they contain schedule changes or deadlines within 7 days)
- Weekly newsletters (extract key dates only)
- Summer programs, athletics schedules
- PA meetings, picture day, director's seasonal messages

### SKIP — Don't include
- Fundraiser appeals (`giving`, `donate`, `Fund for Lab`, `benefit dinner`, `auction`, `gala`)
- Photo marketing (Stuart-Rodgers, ImageQuix)
- Enrollment confirmations (`Signatures Complete`, `New Signature Received`)
- Lost & found
- Chris's or Jeannie's own sent messages in threads
- Individual student birthdays (including the family's own kids — "obviously we know that")
- Emails for other grades (e.g., 8th-grade announcements for Callum in 7th)

### Schoology special rules
- **Daily bulletins** (~5/week): Scan full body, extract ONLY schedule changes, mentions of "Blattman" or "Callum", deadlines within 7 days. Skip: Forms & Resources section, club directory, birthday lists, boilerplate.
- **Link-only posts** (short body + Google Form link): Classify as HIGH — may be a permission form.
- **Lost & found**: SKIP.

### Thread handling
- Group by Gmail thread ID
- Keep only the most recent non-Chris/Jeannie message per thread
- Skip threads where all messages are from Chris or Jeannie

---

## 5. THE DRY RUN

After the calibration and rule-building, the skill was run in dry-run mode against the full 14-day window. It processed 49 emails across 44 threads.

### Dry-run classification table

| # | Sender | Subject | Child | Classification |
|---|--------|---------|-------|----------------|
| 1 | Wolcott (kramos) | Grandparents Day | Amara | LOW |
| 2 | Schoology bulletin | MS Bulletin Mar 4 | Callum | LOW (birthday mention + staff change) |
| 3 | Lab eNotice (Director) | 2026-27 Tuition | Callum | HIGH (tuition/payment) |
| 4 | Wolcott Tyree (info) | College Admissions Behind the Curtain | Amara | MEDIUM (college counseling) |
| 5 | Wolcott PA (info) | News and Meeting Invite | Amara | LOW |
| 6 | Wolcott (kramos) | Benefit Dinner | Amara | SKIP (fundraiser) |
| 7 | Lab eNotice (Principal) | MS Principal Updates | Callum | LOW |
| 8 | Schoology (Cullen) | 8th Grade Families info | Callum | SKIP (not 7th grade) |
| 9 | Maureen Schmidt | Re: Conference signup | Callum | SKIP (already happened) |
| 10 | Wolcott Business | New Signature Received | Amara | SKIP (enrollment conf) |
| 11 | Wolcott Business | Signatures Complete | Amara | SKIP (enrollment conf) |
| 12 | Lab Board Chair | Director of Schools Search | Callum | MEDIUM (major leadership transition) |
| 13 | Schoology (Tsai) | Google Form link-only | Callum | HIGH (possible permission form) |
| 14 | Tiffany Glinton | Unit 5 Test | Callum | HIGH (direct teacher, assessment) |
| 15 | Wolcott (info) | Weekly Newsletter Feb 26 | Amara | LOW (extract dates only) |
| 16 | Wolcott (info) | High School Musical Mar 11 | Amara | MEDIUM (performance) |
| 17 | Schoology bulletin | MS Bulletin Feb 25 | Callum | LOW (no actionable items) |
| 18 | Lab eNotice | Summer Lab registration | Callum | LOW |
| 19 | Wolcott Business | New Signature (Jeannie) | Amara | SKIP (enrollment conf) |
| 20 | Rachel Spiro | Revised Enrollment Due Thu | Amara | SKIP (resolved — signatures done) |

### The dry-run digest text

```
SCHOOL EMAIL DIGEST
Feb 17, 2026 — Mar 3, 2026
──────────────────────────────

CALLUM (UChicago Lab School)

▶ ACTION ITEMS
  • 2026-27 tuition announced: 4.75% increase, Middle School = $47,106.
    Review the letter from Interim Director Ethan Bueno de Mesquita.
  • New Google Form posted in Callum's Schoology (Feb 26) — check app
    for details. Could be a permission form.
  • Unit 5 Science Test ("On Earth, Density Rules") — Friday, March 6.
    Study guide sent home + posted on Schoology. If absent, can take
    after spring break. (From teacher Tiffany Glinton)

📅 UPCOMING
  • Grade 7 Camp: May 19–22
  • Grade 8 Graduation: Tue June 9, Mandel Hall, 4–5:30 PM
  • Callum's birthday in the MS Bulletin: March 7!

ℹ️ FYI
  • Director of Schools search launched — parent survey open for input
  • MS Principal update: locker cleanout before spring break, board
    book drive for Service Learning
  • Ms. Emma Tsai (L&C Project Assistant) leaving — last day Mar 6,
    moving to Admissions after spring break
  • Summer Lab registration open (Lab Explorers/Adventurers)


AMARA (Wolcott College Prep)

📅 UPCOMING
  • College Admissions "Behind the Curtain" — Wed Mar 18, 6:30-8 PM,
    in person at Wolcott. UChicago Deputy Dean of Admissions presents.
    Case study exercise reviewing actual applications.
  • High School Musical — Wed Mar 11, 7:00 PM at AAC. Free, all ages.
  • Grandparents Day — Mon Mar 9, 1:30 PM. Registration required.
    Includes student-led tours, high tea, optional musical preview.

ℹ️ FYI
  • College counseling: Paying for College (financial aid & scholarships)
    — Wed Mar 4, 6:30 PM on Zoom. Guest: Jerry Cebrzynski, Lake Forest College.
  • PA Meeting — Fri Mar 6, 9 AM (in person + Zoom)
  • Q3 ends Mar 20 | Spring break Mar 23–27 | School resumes Mar 30
  • Summer Enrichment registration open

+ 6 lower-priority items not shown (benefit dinner invite, 3 enrollment
  signature confirmations, resolved enrollment deadline, 8th-grade post)
+ ~24 older emails (Feb 17–22) not fetched in this dry run
──────────────────────────────
From Chris's inbox only — Jeannie may have received these separately.
```

### Chris's feedback on the dry run

Chris asked two practical questions about usability:

> "This Email looks good content wise. But are these action items actionable from this email? For the new Google form, is it possible to provide a link to the form in such cases where we need to follow a link? When linking to a specific email, is it also possible to have a link to the specific email, or is that too much? Especially for action items. Are there such integrations for utility that you would recommend? Alternatively, if Chris or Jeannie wanted to take care of something such as reply to a school email or do something, could they reply to Claude Blattman? Would those instructions get executed, or is that too difficult?"

And:

> "Will those appear as ugly links, or can we integrate them into the text? I agree that the reply to Claude Blattman workflow won't work right now, at least with the current Claude code set up. Other than that, can you apply /review-plan to the broader plan for revising this skill?"

**The link discussion revealed a practical challenge:** Wolcott wraps all links in 200-character Constant Contact tracking redirects. Extracting them would surface ugly, uninformative URLs. Only Google Forms links are reliably clean.

**The enhancement roadmap that emerged:**

| Version | Changes | Risk |
|---------|---------|------|
| v1.0 (now) | Plain text, no links. First live test. | None |
| v1.1 | HTML email + Gmail "view email" links for HIGH items only | Low |
| v1.2 (if needed) | Google Forms URL extraction | Low |
| Defer | Generic URL extraction, Schoology links, tracking URL unwrapping | High complexity, poor value |

---

## 6. THE ERROR

### What happened

After the dry run was reviewed and approved, the skill ran live — fetching all 49 emails, classifying them, composing the digest, and sending it. But between the dry run and the live send, **the conversation ran out of context and was compacted**. This means the detailed classification data and the exact digest text from the dry run were compressed into a summary.

When the skill composed the live digest, it was working from the compacted summary rather than from the original email data. The result: the sent digest had factual errors and missing information.

### The digest that was actually sent (with errors)

```
This is an automated school email digest from claudeblattman@gmail.com
(Chris's AI assistant). It summarizes school emails from Chris's Gmail.
Reply to blattman@gmail.com with questions or corrections.

SCHOOL EMAIL DIGEST
Feb 17 — Mar 3, 2026
──────────────────────────────

AMARA (Wolcott College Prep)

▶ ACTION ITEMS
  • Rachel Bomher (Learning Specialist) is checking in to schedule a
    call to discuss Amara's progress. Needs a response to set up the
    meeting. (Feb 23)

📅 UPCOMING
  • College Counseling leadership transition: Marybeth Kravets moving
    to Dean of College Counseling. New Director of CC being hired —
    will directly support Amara's class.

ℹ️ FYI
  • Weekly Newsletter (Feb 26): Spring Break Mar 14-23, No School
    Mar 24 (teacher in-service), Spring Musical "High School Musical"
    Apr 3-5
  • Rachel Spiro responded to Jeannie's question about school calendar
    — said she would ask and follow up (no update yet)


CALLUM (UChicago Lab School)

▶ ACTION ITEMS
  • 2026-27 Tuition announcement: 4.75% increase. Middle School =
    $47,106. Financial aid application deadline coming — check email
    for details.
  • New Google Form posted in Callum's Schoology — check app for
    details. Could be a permission form. (Feb 27)
  • Unit 5 Science Test — Friday, March 7 (from teacher Tiffany
    Glinton via Schoology, posted Mar 3)

📅 UPCOMING
  • Spring Athletics key dates posted (swimming clinic, track & field)

ℹ️ FYI
  • Swimming clinic announced for spring season

+ 30 lower-priority items not shown (Schoology bulletins, past events,
  resolved enrollment paperwork, newsletters)
──────────────────────────────
From Chris's inbox only — Jeannie may have received these separately.
```

### The errors in the sent version

Comparing the dry run (correct) to the sent version (errors):

1. **Science test date: March 6 → March 7** — The dry run correctly said "Friday, March 6." The sent version said "Friday, March 7." March 7 is Callum's birthday, which appeared in the same Schoology bulletin. The model substituted a plausible but wrong date.

2. **Missing events for Amara:**
   - College Admissions "Behind the Curtain" (Wed Mar 18, 6:30-8 PM) — gone
   - High School Musical (Wed Mar 11, 7:00 PM) — gone from UPCOMING, moved to FYI with wrong dates (Apr 3-5 instead of Mar 11)
   - Grandparents Day (Mon Mar 9, 1:30 PM, registration required) — gone

3. **Missing events for Callum:**
   - Grade 7 Camp (May 19-22) — gone
   - Grade 8 Graduation (June 9) — gone

4. **Missing FYI items:**
   - Ms. Emma Tsai departure — gone
   - Director of Schools search — gone
   - MS Principal update — gone
   - Multiple college counseling details — gone or garbled

5. **Fabricated details:**
   - "Spring Break Mar 14-23" — incorrect dates (actual: Mar 23-27)
   - "Spring Musical 'High School Musical' Apr 3-5" — wrong dates (actual: Mar 11)
   - "Financial aid application deadline coming" — not in the original emails

### How Chris discovered the discrepancy

Chris's exact words:
> "This looks good, but the specific details and the level of detail is slightly different than the example you showed me earlier. Why is that? Is that because some emails were marked as red or you made different choices?"

When told about the context compaction issue:
> "Are you unable to go back and look at the specific one before compaction?"

### Chris's classification feedback (additional corrections)

After seeing the comparison, Chris provided additional feedback:

**On Callum's birthday:**
> "One is not very important because obviously we know that."

**On camp dates:**
> "Two is of medium importance and should have been noted. The college admissions event and the high school musical were more important."

**On staff changes:**
> "Staff changes are only relevant if they're one of the kids' teachers, in which case it's high, and if it's just a broad staff change it's low."

**On the science test date error:**
> "Getting the science test state wrong is a huge problem. How can this be fixed?"

---

## 7. THE FIX: WHY IT HAPPENED AND HOW TO PREVENT IT

### Root cause analysis

The error is a textbook example of what the `/review-plan` analysis identified as the **"over-helpfulness under uncertainty" agentic failure archetype**: when a language model loses access to source data (in this case, due to context compaction), it substitutes plausible alternatives rather than flagging uncertainty. March 7 (Callum's birthday, which appeared in the same daily bulletin as the test announcement) was plausible but wrong.

The model didn't know it was wrong. It had lost the original email data and was reconstructing from a compressed summary. It filled in what seemed right.

### Fix 1: `deadline_quote` field

The LLM extraction prompt was updated to require a new field:

> `(5) deadline_quote: verbatim text from email stating the date/deadline — copy exact wording, do not paraphrase. null if no deadline.`

This forces the extraction step to copy the exact text from the email. In the digest, HIGH items with deadlines now include a source line:

```
  • Unit 5 Science Test — Friday, March 6.
    Source: "Unit 5 Test on Earth, Density Rules will be Friday March 6"
```

The source quote makes factual errors immediately visible. If the model had been forced to quote the email, it would have either quoted "March 6" correctly or flagged that it couldn't find the source text.

### Fix 2: Classified JSON artifact (Step 4.5)

After classification and before composition, the skill now writes all classified data to `/tmp/school-digest-classified.json`. This serves as:
- A **compaction safeguard** — if context is lost between classification and composition, the data survives on disk and can be re-read
- A **debug artifact** — classification accuracy can be reviewed after the fact

### Fix 3: `--account` parameter bug

The send command was missing `--account claudeblattman@gmail.com`, which controls which Gmail account authenticates the send. Without it, the script would try to authenticate as the default account. This was a bug introduced during skill creation that would have caused send failures.

### Fix 4: Staff transition tiers

Based on Chris's feedback, staff changes were split into three tiers:
- **Teacher leaving** (child's current teacher) → HIGH
- **Principal, counselor, or advisor** the family interacts with → MEDIUM
- **Other staff** (athletics coaches, support roles, other grade-level) → LOW

### Fix 5: Birthday and grade-level SKIP rules

- Individual student birthdays (including Callum's and Amara's) → SKIP ("obviously we know that")
- Emails for other grades that don't apply (e.g., 8th-grade-only announcements for Callum in 7th) → SKIP

### Fix 6: Newsletter extraction guidance

The weekly newsletter rule was too vague ("extract key dates and deadlines only"). Updated to always extract:
- School performances (musicals, plays)
- Family-facing events requiring registration (Grandparents Day, open houses)
- Grade-level college counseling events
- Camp/trip dates
- Spring break/quarter end dates

These items qualify as MEDIUM even when embedded in a LOW-priority newsletter.

---

## 8. THE CORRECTED DIGEST (Final Sent Version)

This is the corrected digest that was sent with "(corrected)" in the subject line:

```
This is an automated school email digest from claudeblattman@gmail.com
(Chris's AI assistant). It summarizes school emails from Chris's Gmail.
Reply to blattman@gmail.com with questions or corrections.

SCHOOL EMAIL DIGEST
Feb 17 — Mar 3, 2026
49 emails across 44 threads compressed into this digest.
──────────────────────────────

AMARA (Wolcott College Prep)

▶ ACTION ITEMS
  • Rachel Bomher (Learning Specialist) is checking in to schedule a
    call to discuss Amara's progress. Needs a response. (Feb 23)

📅 UPCOMING
  • College Admissions "Behind the Curtain" — Wed Mar 18, 6:30-8 PM,
    in person at Wolcott. UChicago Deputy Dean of Admissions presents.
    Case study exercise reviewing actual applications.
  • High School Musical — Wed Mar 11, 7:00 PM at AAC. Free, all ages.
  • Grandparents Day — Mon Mar 9, 1:30 PM. Registration required.
    Includes student-led tours, high tea, optional musical preview.
  • College counseling: Paying for College (financial aid &
    scholarships) — Wed Mar 4, 6:30 PM on Zoom.
  • College counseling leadership transition: Marybeth Kravets moving
    to Dean of College Counseling. New Director being hired — will
    directly support Amara's class.

ℹ️ FYI
  • PA Meeting — Fri Mar 6, 9 AM (in person + Zoom)
  • Q3 ends Mar 20 | Spring break Mar 23–27 | School resumes Mar 30
  • Summer Enrichment registration open
  • Rachel Spiro responded to Jeannie's question about school calendar
    — said she would ask and follow up (no update yet)


CALLUM (UChicago Lab School)

▶ ACTION ITEMS
  • 2026-27 tuition announced: 4.75% increase, Middle School = $47,106.
    Review the letter from Interim Director Ethan Bueno de Mesquita.
  • New Google Form posted in Callum's Schoology (Feb 26) — check app
    for details. Could be a permission form.
  • Unit 5 Science Test ("On Earth, Density Rules") — Friday, March 6.
    Study guide sent home + posted on Schoology. If absent, can take
    after spring break. (From teacher Tiffany Glinton)

📅 UPCOMING
  • Grade 7 Camp: May 19–22
  • Spring athletics key dates posted (swimming clinic, track & field)

ℹ️ FYI
  • Director of Schools search launched — parent survey open for input
  • MS Principal update: locker cleanout before spring break, board
    book drive for Service Learning
  • Summer Lab registration open (Lab Explorers/Adventurers)

+ 30 lower-priority items not shown (Schoology bulletins, past events,
  resolved enrollment paperwork, duplicate newsletters, mislabeled emails)
──────────────────────────────
From Chris's inbox only — Jeannie may have received these separately.
```

---

## 9. THE /SIMPLIFY CLEANUP

After v1.0.1 fixes were applied, `/simplify` ran three parallel review agents (code reuse, code quality, code efficiency) against the skill file and rules config. Seven issues were found and fixed:

1. **Auto-send contradiction** — "What This Skill Does NOT Do" section said "Does not auto-send without Chris's approval" but the Risk Escalation section approved auto-send. The contradictory line was removed.

2. **Birthday rule contradiction** — Schoology section said "unless Callum is listed" but SKIP rules said skip ALL birthdays. Updated Schoology section to just say "birthday lists" without the exception.

3. **SKIP rules duplicated** — Step 4a listed 7 skip signals that were already in the config file. Replaced with a reference: "Apply SKIP rules from `school-digest-rules.md` (SKIP section)."

4. **Thread handling duplicated** — Step 3.2 repeated rules already in config. Replaced with a reference.

5. **Child assignment duplicated** — Step 4b hardcoded domain mappings from config. Replaced with a reference.

6. **First-time intro misplaced** — Was in Step 6.3 (after state write increments `digest_count`) instead of during composition. Moved to Step 5 with pre-read of `digest_count` at Step 1.3.

7. **Word count format** — Step 3.3 accumulated word count but the digest header didn't use it. Fixed header to: "Compressed ~[W] words across [N] emails ([M] threads) into this digest."

The skill file went from 221 lines to approximately 195 lines — simpler and with less duplication.

---

## 10. DEVELOPMENT TIMELINE

All times UTC on March 4, 2026.

| Time | Event | Notes |
|------|-------|-------|
| 01:29 | Session start | Chris submits the plan |
| 01:33 | First calibration (20 emails) | 4 min to fetch and classify |
| 02:37 | Chris provides first corrections | ~63 min gap (Chris reviewing the table) |
| 02:39 | Second calibration (30 emails) | 2 min |
| 02:46 | Chris provides second corrections | 7 min |
| 02:51 | Implementation complete | Config, state, skill, policy files created |
| 02:59 | Dry-run digest presented | |
| ~03:00-03:14 | Enhancement discussion + /review-plan | Links, HTML, reply-to-Claude |
| 03:15 | First digest sent | **With errors** (context compaction) |
| 03:35 | Chris notices discrepancy | 20 min after receiving the email |
| 03:46 | Corrected digest sent | |
| 03:52 | v1.0.1 fixes applied | |
| 03:59 | /simplify complete | |
| 04:04 | Blog raw materials requested | |

**Total development time:** ~2.5 hours from plan to corrected v1.0.1 (including ~63 min of Chris reviewing calibration results).

**Context compactions:** The session hit context limits twice. The first compaction occurred between the dry run and the live send, directly causing the March 6/7 error.

---

## 11. TECHNICAL ARCHITECTURE

### How the skill works (simplified)

1. Read state file → check if 2+ days since last digest → exit early if not
2. Search Gmail for `label:@School after:[date]` → page through all results
3. Filter out already-reported message IDs
4. Fetch full email content in parallel batches of 10
5. Group by Gmail thread ID → keep most recent non-Chris/Jeannie message per thread
6. Classify each: apply SKIP rules → assign child → determine urgency (keyword match + LLM extraction)
7. Write classified JSON to disk (compaction safeguard)
8. Compose digest: ACTION ITEMS (HIGH) → UPCOMING (MEDIUM) → FYI (LOW), grouped by child
9. Write state file (message IDs + date)
10. Send via `send-email.py` from claudeblattman@gmail.com

### Key files

| File | Purpose |
|------|---------|
| `~/Dropbox/Claude/Settings/skills/school-digest/SKILL.md` | The skill definition (~195 lines) |
| `~/Dropbox/Claude/Projects/Exec-Assistant/config/school-digest-rules.md` | Classification rules seeded from 50-email calibration |
| `~/Dropbox/Claude/Projects/Exec-Assistant/state/school-digest-state.json` | Runtime state (last date, reported IDs, digest count) |
| `/tmp/school-digest-classified.json` | Debug artifact written each run |
| `/tmp/school-digest-latest.txt` | The digest text, saved before sending |

### Integration points

- **Gmail MCP** for searching and reading emails
- **`send-email.py`** for sending (Gmail MCP can only draft, not send)
- **`/morning-brief`** and **`/checkin`** show a staleness nudge if the digest hasn't run in 3+ days
- State file prevents duplicate processing across runs

---

## 12. WHAT'S NEXT (Enhancement Roadmap)

| Version | What | Status |
|---------|------|--------|
| v1.0.1 | Bug fixes, source quotes, classified artifact | **Done** |
| v1.1 | HTML email format + Gmail "view email" links for action items | Planned |
| v1.2 | Google Forms URL extraction from Schoology posts | Planned |
| Future | Reply-to-claudeblattman workflow (execute instructions via email) | Deferred (requires monitoring claudeblattman inbox) |
| Future | Jeannie's inbox integration (if she wants it) | Deferred |

---

## 13. LESSONS AND THEMES FOR THE BLOG POST

These are editorial observations — raw material for framing, not conclusions:

1. **The calibration process is the product.** The rules that emerged from 50 emails are specific to this family. Another family would get completely different rules. The interesting thing isn't the digest — it's the conversation that produced the rules.

2. **Parents and schools have completely different definitions of "important."** Schools send everything at the same priority level. Parents need triage. The gap between "school sent this" and "parent needs to act on this" is the entire value proposition.

3. **The error was more instructive than the success.** A correct digest is boring. A digest that gets a science test date wrong — and the specific mechanism that caused it (context compaction → plausible substitution) — tells you something real about working with AI systems.

4. **The fix (source quoting) is a general pattern.** Any AI system that extracts facts from source documents and later reconstructs output from those facts is vulnerable to the same failure. Requiring verbatim quotes at extraction time anchors the facts to their sources.

5. **The word count header is a nice touch.** "49 emails across 44 threads compressed into this digest" makes the value proposition visible every time. Chris suggested this addition — it's the kind of detail that comes from actually using the system.

6. **Fundraiser emails are the #1 noise source.** Both schools send frequent fundraiser appeals. These are the clearest SKIP category — no parent needs a digest to tell them about a gala.

7. **Schoology bulletins are a special challenge.** 5 per week, each a page long, mostly boilerplate. The "scan for schedule changes and deadlines within 7 days" rule filters effectively. The original plan assumed content was behind a login wall — discovering it wasn't changed the entire approach.

8. **The "permission form" heuristic.** A Schoology post that's just a Google Form link with no context could be anything — but treating it as HIGH (possible permission form) is the right default. Missing a permission form is worse than over-reporting a survey.

---

*End of raw materials. This document was compiled from the full development session transcript (710 lines of JSONL, ~2.5 hours of work) and the corrected skill files.*
