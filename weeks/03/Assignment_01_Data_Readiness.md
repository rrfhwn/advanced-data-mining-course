# Assignment 1 — Can We Trust This Dataset?

**Draft for instructor review; not a released deadline or retrospective announcement.** This is the first of four equally weighted assignments, worth 25% of the course grade. Use the instructor's confirmed release instructions for the deadline, submission channel, expected effort, and collaboration/AI-use rules. Do not assume the planning window means this brief was already issued.

## Question and supplied material

A colleague wants to mine this retail extract and asks whether it is adequate for a defined investigation, which relationships deserve attention, and which customer histories should receive source review first. A review candidate need not be an error.

Use the versioned retail extract already loaded automatically by Lectures 1–3. Preserve the original invoice-line table. Use one customer ID as the anomaly-scoring unit and record the eligible population. The core comparison uses recency, distinct-invoice frequency, and positive recorded value under a documented preparation policy. Compare both methods on exactly the same IDs and features with **ten review slots**. You may challenge the default policy or representation, but keep the comparison fair and explain coverage changes. No new dataset download or manual upload is required.

The [Week 3 notebook](Week_03_Anomalies_Review_Decisions.ipynb) supplies loading, feature-construction, baseline, forest, list-comparison, and source-inspection examples. Weeks 1–2 supply audit and exploratory examples. Adapt working code, but explain your own question, decisions, evidence, and limitations. An unchanged plot without interpretation is not a complete analysis.

## Required evidence in one executable notebook

1. State one concrete investigation question, provenance/license, observation units, available window, and sampling limitations. Audit missingness, exact duplicates, ranges, and an appropriate cross-field condition—for example, cancellation prefixes alongside signed quantities. Distinguish a policy exclusion from an established error.
2. Preserve raw data and justify at least three consequential preparation decisions. Include one suspicious observation retained or left unresolved, with the evidence needed before a repair. Explain why unknown IDs cannot be aggregated into reliable customer histories, or justify another identity policy.
3. Produce two useful visualizations and one subgroup comparison, stating denominators and limits. Country differences, for example, can describe this extract but do not estimate national retail behavior. Do not infer causation from a difference in summaries.
4. Compare a robust median/MAD baseline and Isolation Forest on the same scoring population and representation. Explain any unusable zero-MAD columns, nonfinite-value handling, score direction, and how ranking selects exactly ten IDs. Do not call a score an error probability.
5. Inspect five selected customer histories, including a method disagreement where available. Use original-unit profiles and source invoice lines. Identify likely issues, plausible rare cases, and unresolved cases only where evidence supports them; you do not have to force every category into the review sheet.
6. Change one preparation, representation, or model setting while keeping other choices fixed where possible. Compare top-ten membership using a named measure and denominator; inspect an entering/leaving or boundary case. If you change population coverage, separate that effect from ranking sensitivity. A budget-only comparison can supplement this, but does not replace a preparation/representation/model sensitivity check.
7. Finish with a short data-readiness recommendation, remaining limitations, and an actionable review step. Specify which claims should be postponed until more evidence is available. A carefully supported negative or uncertain result is acceptable.

## Reproducibility and interpretation

Run top to bottom in a fresh kernel, retain supporting outputs in your submitted notebook, and state the versions, seed, feature policy, and data version/hash. Keep explanations beside the relevant evidence. No GPU, private account, external fraud labels, or positive detection result is required. Ground-truth anomaly labels are absent, so model agreement is not accuracy and cannot supply precision/recall.

The quality of method, data understanding, analysis, interpretation, reproducibility, and critical reflection matters—not the number of dramatic candidates. The proposed common rubric, pending confirmation with release, allocates 30% to method correctness, 20% to data understanding/preparation, 25% to evaluation/robustness, 15% to interpretation/limitations, and 10% to reproducibility/clarity. The instructor may ask you to explain a decision or result to verify understanding and independent work. This is not a fifth assessment component.
