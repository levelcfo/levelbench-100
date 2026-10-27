# LevelBench-100: Evaluation Methodology, Dataset Provenance & Reproducibility

## 1. Benchmark Scope & Task Construction
LevelBench-100 evaluates 38 frontier LLMs and multi-file CLI harnesses across **100 deterministic accounting, tax, and month-end close checks** spanning **15 multi-tab Excel (`.xlsx`) close workbooks** (in `workbooks/`) and **31 structured task rubrics** (`tasks_31_rubrics.json`).

## 2. Data Provenance & De-Identification
All 15 close workbooks and 31 task scenarios are derived from real US SMB general-ledger closes (construction, healthcare, e-commerce, real estate, and SaaS) and de-identified using deterministic entity-name substitution and scalar perturbation while preserving exact double-entry trial-balance identities ($Assets = Liabilities + Equity$), subledger-to-GL reconciliation ties, and planted accounting defects (`error_taxonomy_30_modes.json`).

## 3. Deterministic Scoring Criteria (Zero LLM-as-a-Judge Variance)
Unlike open-ended text benchmarks, LevelBench-100 uses **100% deterministic programmatic graders** (`checks_100_atomic.json`):
- **Trial Balance & Journal Footing**: Exact cent-level numeric equality ($sum Debits = sum Credits$).
- **Planted Defect Detection**: Exact cell/transaction ID recall and precision against ground-truth ledger defects (duplicate vendor bills, unrecorded retainage, payroll tax clearing drift, cutoff errors).
- **Bad-Entry Rate (Safety Metric)**: Any hallucinated journal entry or unbalanced posting that corrupts a clean control account increments the bad-entry counter.

## 4. Reproducibility & Harness Isolation
All prompts, temperature settings ($T = 0.0$ where supported), token budgets, and per-condition results (raw model vs. CLI harness vs. deterministic verification checklist) are published in `leaderboard_38_models.json` and archived under Zenodo DOI `10.5281/zenodo.19448302`.

## 5. Known Limitations
- Focuses on US GAAP / IRS tax rules (Form 1120-S, 1065, Schedule C, MACRS/Bonus depreciation) rather than IFRS.
- Workbook tasks evaluate batch close artifacts and read-only MCP tool calls rather than live multi-user ERP concurrency.
