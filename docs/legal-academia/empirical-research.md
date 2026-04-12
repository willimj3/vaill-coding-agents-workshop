# Empirical Legal Research

**Using AI for research design, data cleaning, statistical analysis, and visualization — with Claude Code as your research assistant that writes and runs code.**

Empirical legal research has a barrier that most legal scholarship does not: it requires code. Whether you are analyzing sentencing data, surveying judicial opinions, or running regressions on court filing patterns, somewhere in the process you need to write a script, clean a dataset, or generate a chart. For law faculty without a quantitative methods background, that barrier can feel insurmountable.

AI lowers that barrier dramatically. Claude Code can write Python or R scripts, execute them against your data, produce visualizations, and explain what the results mean — all in plain English conversation. You describe what you want to analyze; the AI writes the code and runs it. Your job is to understand the output, verify it makes sense, and interpret the results with your domain expertise.

!!! warning "You are the methodologist"
    AI can write code and run statistics, but it cannot replace your judgment about research design, variable selection, or what the results mean for legal policy. Verify every statistical claim. Check that the code does what you think it does. When in doubt, consult a colleague with quantitative training or your institution's research methods center.

---

## What This Looks Like in Practice

Before getting into the workflow details, it helps to see what AI-assisted empirical research actually produces. In January 2026, Stanford political economist Andy Hall gave Claude Code a single prompt: replicate and extend a published PNAS paper on vote-by-mail policy. An independent audit by UCLA PhD candidate Graham Straus found that Claude Code:

- **Replicated the original paper's published estimates exactly**
- **Collected new data** across three states for 2020-2024 with high accuracy (29/30 counties correct on treatment dates)
- **Ran the extended analysis** with difference-in-differences, producing results nearly identical to the human replication (main coefficient: 0.003 vs. 0.004)
- Completed the work in **under an hour** with minimal oversight

But the audit also found real problems: Claude missed gubernatorial and senatorial data for two states, produced lower-quality work when going beyond the original methodology, and failed to keep adequate records of data collection decisions.

The takeaway for law faculty: AI can dramatically accelerate the mechanical parts of empirical research — data collection, cleaning, replication, standard statistical analysis. But it requires expert oversight, especially when the work moves beyond well-defined tasks into novel analysis. The combination of your domain expertise and the agent's computational capability is where the real value lies.

[:octicons-arrow-right-24: Read the full Straus & Hall audit (PDF)](../papers/Straus_Hall_Claude_Audit.pdf){ target="_blank" }

---

## Why This Matters

Empirical legal scholarship is growing. Journals increasingly publish quantitative work — analysis of case outcomes, survey data on legal attitudes, natural language processing of judicial opinions. But many law faculty were trained in doctrinal methods and may not have taken a statistics course since college, if at all.

AI does not give you a statistics education. What it gives you is a capable research assistant that can:

- Help you design surveys and data collection instruments
- Write data cleaning scripts that handle messy real-world data
- Run standard statistical analyses and explain the output
- Generate publication-quality charts and tables
- Critique your methodology and flag potential problems
- Translate between plain English research questions and statistical procedures

The combination of your legal expertise and AI's computational capability is more powerful than either alone.

---

## The Workflow

### Step 1: Research design

Before touching any data, use AI to help refine your research design. This is a conversation, not a one-shot prompt — expect to go back and forth several times.

```text
I am a law professor planning an empirical study. Here is my research
question:

Does the implementation of risk assessment algorithms in pretrial
detention decisions reduce racial disparities in bail outcomes?

I have access to pretrial detention records from three county courts
over a five-year period (2019-2024). The records include defendant
demographics, charge type, risk assessment score (where available),
bail amount set, and detention outcome.

Help me think through the research design:
1. What is my identification strategy? How can I isolate the effect
   of risk assessment adoption from other changes happening in these
   courts over the same period?
2. What are the key variables I need to control for?
3. What statistical methods are appropriate?
4. What are the major threats to internal validity?
5. What sample size considerations should I be aware of?

Be specific and critical. If my research design has obvious weaknesses,
tell me directly.
```

The AI will often suggest approaches you had not considered — difference-in-differences designs, instrumental variables, or robustness checks that strengthen the study. It may also flag problems: confounders you missed, data limitations that undermine a particular strategy, or sample size issues that make certain analyses underpowered.

### Step 2: Data cleaning with Claude Code

This is where Claude Code earns its keep. Real-world legal data is messy — inconsistent date formats, missing values, duplicate records, coding errors. Data cleaning is tedious, error-prone, and necessary. Claude Code can do it in minutes.

!!! tip "Claude Code for data work"
    Claude Code can read files on your computer, write scripts, and execute them. For empirical research, this means you can point it at a CSV file of court records and say "clean this data" — and it will write and run a Python script that handles the cleaning. See the [Setup Guide](../setup/index.md) if you have not installed Claude Code yet.

A typical data cleaning conversation in Claude Code:

```text
I have a CSV file at ~/research/pretrial-data/raw_records.csv with
pretrial detention records. Please:

1. Load the file and show me the first 10 rows and column names
2. Report the number of rows, columns, and data types
3. Check for missing values in each column and report the percentage
4. Identify any obvious data quality issues (duplicate case IDs,
   impossible dates, values that look like coding errors)
5. Propose a cleaning plan before executing it — I want to approve
   each step
```

The key instruction is number 5: **propose a cleaning plan before executing it.** You want to review what the AI plans to do with your data before it does it. Dropping rows with missing values, for example, might be appropriate or might introduce selection bias — that is a judgment call that requires your domain knowledge.

### Step 3: Analysis

Once your data is clean, describe the analysis you want in plain English. Claude Code will write the appropriate statistical code and run it.

```text
Using the cleaned dataset, run the following analyses:

1. Descriptive statistics: For each county, calculate the mean bail
   amount and detention rate by race, before and after risk assessment
   adoption. Present as a formatted table.

2. Difference-in-differences: Estimate the effect of risk assessment
   adoption on racial disparities in detention rates. Use county
   fixed effects and year fixed effects. Cluster standard errors
   at the county level.

3. Robustness checks:
   - Repeat the analysis excluding drug charges
   - Test for pre-trends in the pre-adoption period
   - Run a placebo test using a county that never adopted
     risk assessment

For each analysis, show me the code, run it, and explain the results
in plain English. Flag any results that seem surprising or that I
should investigate further.
```

### Step 4: Visualization

Ask Claude Code to generate charts for your paper or presentation.

```text
Create the following visualizations from our analysis:

1. A parallel trends plot showing detention rates by race for
   treatment and control counties in the pre-adoption period

2. A coefficient plot showing the main diff-in-diff estimate
   and the robustness check estimates with 95% confidence intervals

3. A table formatted for journal submission showing the regression
   results with standard errors, significance stars, and
   observation counts

Use a clean, publication-ready style. No gridlines. Black and white
friendly (it needs to work in print). Label axes clearly.
Save all figures as both PNG (300 DPI) and PDF.
```

### Step 5: Methodology critique

Before finalizing your paper, ask AI to critique your approach. This is the empirical research equivalent of the [plan review technique](../workflows/plan-review-browser.md).

```text
I am about to submit a paper using the methodology described above.
Act as a skeptical peer reviewer with expertise in causal inference
and criminal justice data.

Critique my research design. Specifically:
1. Are there confounders I have not addressed?
2. Is my identification strategy convincing? What are the
   strongest objections?
3. Are my robustness checks sufficient, or would a reviewer
   want additional tests?
4. Are there alternative explanations for my results that I
   should address in the paper?
5. What would you flag in a referee report?

Be direct. I would rather hear problems now than in a revise-and-
resubmit letter.
```

---

## Limitations

**Statistical claims require verification.** AI can produce confident-sounding statistical output that contains errors — wrong degrees of freedom, misspecified models, incorrect standard errors. Always review the code, not just the output. If you are not comfortable reading the code, ask the AI to explain each line, and consult a methods colleague for high-stakes analyses.

**AI does not understand your data.** The AI can manipulate numbers, but it does not know what the numbers mean in context. A variable called "disposition" might mean case disposition or character disposition — you know the difference, the AI does not. Review variable definitions and coding decisions carefully.

**Causal inference requires human judgment.** The AI can run a regression, but deciding whether the results support a causal claim depends on research design, institutional knowledge, and domain expertise that the AI does not have. The AI can suggest methodological approaches, but the judgment about which approach is appropriate for your specific context is yours.

**Reproducibility matters.** If you are using Claude Code to run analyses, save all scripts. Ask Claude Code to write clean, commented scripts that a research assistant (or future you) can understand and rerun. Include a README file in your project that documents the analysis pipeline.

---

## CLAUDE.md Template for Empirical Research Projects

If you are using Claude Code for an empirical project, put a CLAUDE.md file in your project directory. This gives Claude Code persistent context about your research every time you start a new session.

```markdown
# Empirical Research Project: [Title]

## Project overview
[One paragraph describing the research question and approach]

## Data
- Source: [Where the data comes from]
- Location: data/raw/ contains original files; data/clean/ contains
  processed files
- Key variables: [List the most important variables and what they mean]
- Known data issues: [Any known problems with the data]

## Methodology
- Design: [e.g., difference-in-differences, regression discontinuity]
- Primary outcome: [What you are measuring]
- Key controls: [Variables you control for]
- Clustering: [How you handle standard errors]

## Code conventions
- Language: Python (pandas, statsmodels, matplotlib)
- All scripts go in scripts/ directory
- All output goes in output/ directory
- Name scripts sequentially: 01_clean.py, 02_describe.py,
  03_analyze.py, 04_visualize.py
- Include comments explaining each analytical decision
- Save all intermediate datasets so analysis is reproducible

## Rules
- Never drop observations without asking me first
- Always show me the code before running destructive operations
  on the data
- When reporting results, include sample sizes, standard errors,
  and confidence intervals
- Flag any result that is statistically significant at p < 0.05
  but has a small effect size
- If a robustness check produces different results from the main
  analysis, alert me immediately
```

---

## Example: Analyzing Sentencing Data

Here is a concrete example of what an empirical research workflow looks like in practice. Suppose you have obtained sentencing data from a state court system and want to analyze racial disparities in sentence length.

**Start the conversation:**

```text
I have sentencing data from [State] courts, 2018-2023, in a CSV file
at ~/research/sentencing/data/raw_sentences.csv.

Each row is a case. Key columns: case_id, defendant_race, defendant_age,
defendant_gender, charge_category, offense_level, prior_record_score,
judge_id, sentence_months, sentence_type (prison/probation/fine),
county, year.

I want to analyze whether there are racial disparities in sentence
length after controlling for legally relevant factors. Walk me through
this step by step.
```

Claude Code will typically propose a pipeline: load and inspect the data, check for missing values, run descriptive statistics, estimate a regression model with appropriate controls, test for robustness, and generate visualizations. At each step, you review the code and the output before moving on.

The key insight: you bring the legal knowledge (what counts as a legally relevant sentencing factor, how prior record scores work in this jurisdiction, what the sentencing guidelines say). The AI brings the computational capability (writing clean analysis code, running the statistics, generating the charts). Neither is sufficient alone. Together, they produce work that would take a solo researcher much longer.

---

## Example: Replicating and Extending a Published Study

Replication studies are increasingly valued in empirical legal scholarship. Claude Code is well-suited to this work because the task is well-defined: download an existing dataset, reproduce published results, and extend the analysis with new data. This is exactly the workflow that Straus and Hall (2026) tested in their [audit of Claude Code](../papers/Straus_Hall_Claude_Audit.pdf).

Here is how to structure a replication and extension project.

### Set up the project

Create a project folder and a CLAUDE.md file that describes the original paper, the replication goal, and your extension plan:

```markdown
# Replication & Extension: [Original Paper Title]

## Original paper
- Authors: [names]
- Published: [journal, year]
- DOI: [link]
- Replication data: [repository URL]

## Replication goal
Reproduce Tables [X] and [Y] from the original paper using the
authors' replication data. Verify that our estimates match the
published results before proceeding to any extension.

## Extension plan
[Describe what new data you will add and what new analysis you
will run. Be specific about the time period, geography, or
variables you are extending.]

## Methodology
- Design: [e.g., difference-in-differences, panel fixed effects]
- Software: Python (pandas, statsmodels) or R (fixest, tidyverse)
- Clustering: [how standard errors are clustered]

## Rules
- Replicate first, extend second. Do not begin the extension
  until the replication matches the published results.
- Document every data collection decision in a log file.
- When collecting new data, record the source URL and date
  accessed for every data point.
- Never silently drop observations. Flag missing data and ask
  me how to handle it.
- Save all intermediate datasets so every step is reproducible.
```

### Step 1: Replicate the original results

```text
Download the replication data from [repository URL]. Load the
main analysis dataset. Replicate Tables [X] and [Y] from the
original paper exactly.

For each table:
1. Show me the regression specification you are running
2. Report your coefficients, standard errors, and sample sizes
3. Compare them to the published values
4. Flag any discrepancies, no matter how small

Do not proceed to the extension until we have confirmed the
replication matches.
```

This step matters because it verifies your setup before you invest time in new analysis. In the Straus & Hall audit, Claude Code replicated the original estimates exactly — which gave confidence that the data pipeline was correct before moving on.

### Step 2: Collect and integrate new data

```text
Now extend the analysis. We need [describe new data — e.g.,
county-level election results for 2020, 2022, and 2024 from
California, Utah, and Washington].

For each data point you collect:
1. Record the source URL
2. Record the date accessed
3. Record any judgment calls (e.g., how you handled missing
   values or ambiguous codings)

Save the collection log to data/collection_log.md.
After collecting, merge the new data with the original dataset
and show me summary statistics comparing the original and
extended samples.
```

!!! warning "Audit your agent's data collection"
    In the Straus & Hall audit, Claude Code collected treatment data with high accuracy (29/30 counties correct) but silently omitted senatorial and gubernatorial data for two states. The agent did not flag the omission — the human auditor discovered it. Always verify that the new dataset contains what you expected, and cross-check a sample of data points against the original sources.

### Step 3: Run the extended analysis

```text
Using the merged dataset (original + extension), re-run the
main specifications from Tables [X] and [Y] on the full sample.

Then run these robustness checks:
1. The original specification on only the new data (extension
   period only)
2. A pre-trends test for the pre-treatment period
3. [Any additional checks relevant to your extension]

For each result, compare to the original paper's estimates.
Discuss whether the extended results are consistent with the
original findings or suggest a different pattern.
```

### Step 4: Document everything

This is where the Straus & Hall audit found the biggest gap: Claude Code did not keep adequate records of its data collection decisions. Make documentation an explicit requirement.

```text
Create a README.md in the project root that documents:

1. The original paper being replicated (full citation)
2. What data was collected for the extension, from where,
   and when
3. Every judgment call made during data collection or cleaning
4. The full list of scripts, in execution order, with a
   one-line description of what each does
5. How to reproduce every table and figure from start to finish

Also save all scripts with clear comments explaining each
analytical decision.
```

### What this workflow produces

When done well, this workflow produces a replication and extension that is:

- **Verifiable** — every step is documented and reproducible
- **Fast** — the mechanical work (data collection, cleaning, running regressions) takes hours instead of weeks
- **Auditable** — the collection log and scripts make it possible for a co-author or reviewer to check every step

The expert judgment — choosing the right identification strategy, interpreting results, deciding what robustness checks matter, writing up the findings — remains entirely yours. The agent handles the computational labor.

[:octicons-arrow-right-24: Read the full Straus & Hall audit (PDF)](../papers/Straus_Hall_Claude_Audit.pdf){ target="_blank" }

---

## Next Steps

<div class="grid cards" markdown>

-   **Set up Claude Code**

    ---

    Install and configure Claude Code to run analysis scripts on your machine.

    [:octicons-arrow-right-24: Setup Guide](../setup/index.md)

-   **Configure your project**

    ---

    Write a CLAUDE.md file that gives Claude Code context about your research.

    [:octicons-arrow-right-24: Your CLAUDE.md](../toolkit/claude-md.md)

-   **Review your methodology**

    ---

    Use the plan review technique to stress-test your research design before committing to it.

    [:octicons-arrow-right-24: Stress-Test Any Plan](../workflows/plan-review-browser.md)

</div>
