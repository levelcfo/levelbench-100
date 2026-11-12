# LevelBench-100 (v5.0.0): AI Accounting, Fractional CFO & Operations Benchmark

> **NON-COMMERCIAL EVALUATION LICENSE NOTICE**: This dataset and benchmark suite are published under the **Level Personal, Academic & Non-Commercial Evaluation License v1.0 (Commercial Use Requires License from sam@levelcfo.com)** ([full license & IP notice](https://levelcfo.com/data/benchmarks/cases/LICENSE_AND_IP_NOTICE.txt)). Free for personal operator review, individual CPA/CFO inspection, and non-commercial academic evaluation only. **Commercial AI labs, foundation model trainers, RL environment builders, data brokers, and commercial software vendors are strictly prohibited from training on, redistributing, or commercially benchmarking with these datasets or cases without a written commercial license.** For commercial licensing, model training rights, enterprise RL environments, or access to Level's expanded vault across 2,200+ SMB cleanups, contact **sam@levelcfo.com**.

Release: **5.0.0**

- **Canonical Interactive Benchmark**: [https://levelcfo.com/benchmarks/agentic-accounting/](https://levelcfo.com/benchmarks/agentic-accounting/)
- **36 Common AI Accounting, CFO & Operations Mistakes**: [https://levelcfo.com/benchmarks/agentic-accounting/ai-error-taxonomy/](https://levelcfo.com/benchmarks/agentic-accounting/ai-error-taxonomy/)
- **40 Anonymized SMB Client Close Case Studies (.xlsx / .csv / .json)**: [https://levelcfo.com/benchmarks/agentic-accounting/smb-case-worlds/](https://levelcfo.com/benchmarks/agentic-accounting/smb-case-worlds/)
- **Full Benchmark Deep-Dive Article**: [https://levelcfo.com/blog/levelbench-100-ai-accounting-cfo-benchmark/](https://levelcfo.com/blog/levelbench-100-ai-accounting-cfo-benchmark/)
- **Hugging Face Dataset**: [https://huggingface.co/datasets/LevelCFO/levelbench-100](https://huggingface.co/datasets/LevelCFO/levelbench-100)
- **Hugging Face Leaderboard Space**: [https://huggingface.co/spaces/LevelCFO/levelbench-100](https://huggingface.co/spaces/LevelCFO/levelbench-100)
- **GitHub Repository**: [https://github.com/levelcfo/levelbench-100](https://github.com/levelcfo/levelbench-100)
- **Published by**: [Level](https://levelcfo.com) (always-on bookkeeping, month-end close, tax, and fractional CFO service for contractors, service businesses, and ecommerce brands)

---

## Executive Summary: Can AI Close Real SMB Books?

We evaluated **58 live multi-cloud AI model and Level Playbook arms** across **25 foundation, fast-worker, and open-weight models** (including Google Gemini 4 Carbon, Argon, GPT-6.1 Sol/Terra, GPT-6 Astra, Claude Sonnet/Haiku 5.5, Moonshot Kimi K3.1, Qwen 3 Next 80B, DeepSeek V3.2/R1, Llama 4 Maverick, and Mistral Large 3) on **60 anonymized SMB close worlds (122 tasks, 924 binary checks)** and our **374-world RLVR vault (752 tasks, 5,923 binary checks)**, alongside **40 downloadable SMB close case studies** (84 close tasks, 588 binary rubric checks), **36 common AI accounting error patterns** (95 automated close guardrails), and **14 production accounting, payroll, and field-service portals** (84 portal-gate trials).

### Headline Findings

1. **Gemini 4 Carbon Sweeps #1 & #2 Unassisted Across 924 Close Checks (95.24% & 95.13%)**:
   - **Gemini 4 Carbon (Low)** ranks #1 unassisted at **95.24%** accounting accuracy (**95.24%** strict precision, 0 formatting misses, 88.01s p50, $0.063/task), followed by **Gemini 4 Carbon (Medium)** at **95.13%**, **Gemini 4 Argon (Low)** at **94.70%**, **GPT-6.1 Sol (High)** at **93.29%**, and **GPT-6 Astra (Medium)** at **92.86%**.
   - **Moonshot Kimi K3.1** leads open-weight models at **81.28%** raw, ahead of **Qwen 3 Next 80B** (**71.10%**), **DeepSeek V3.2** (**69.81%**), **Claude Haiku 5.5** (**66.02%**), **Llama 4 Maverick** (**62.55%**), **Mistral Large 3** (**58.12%**), and **Gemini 2.5 Flash-Lite** (**52.38%**; **Claude Sonnet 5.5** scores **73.39%** on our 25-world slice vs **93.55%** Carbon Low).
   - **Shared `maxOutputTokens=8192` Truncation Catch**: Because Vertex AI counts internal thinking tokens inside `maxOutputTokens`, an 8,192-token cap silently truncates **21.3% (26/122)** of Carbon Medium tasks and **100%** of Carbon High tasks until raised to 65,536 tokens.
2. **Multi-File Agentic CLI Harnesses Reach 100.0% (16/16) When Guided by Level Checklists**:
   - Across 6 receipt-verified CLI runs on our 16-check multi-file landscaping close package, **Codex CLI (GPT-5.6 Terra)** completed all **16/16 checks (100.0%)** in **27.22s**, **Codex CLI (GPT-6.1 Sol)** in **36.46s**, and **Antigravity CLI (Gemini 4 Argon Low)** in **37.50s**.
3. **AI + Level Playbooks (2,200+ Past Experiences) + Operator Review Reaches 100.00% Across All 5,923 Checks at $0.0039/Close**:
   - All **25 Level Playbook arms** score **100.00%**, including **Gemini 2.5 Flash-Lite** jumping from **52.37% raw to 100.00% (5,923 / 5,923 checks, +47.63 pp lift, 417 route overrides, 131 hallucinations quarantined)** in **1.10s p50 at $0.0039/close**.
4. **14-Portal Browser-Use Benchmark (84 Portal-Gate Trials)**:
   - Across QuickBooks Online, BuildOps, ServiceTitan, Housecall Pro, LMN, Roofr, MarketSharp, Rippling, Gusto, Ramp, Brex, Settle, Finaloop, and Shopify:
   - **Unassisted Vision Browser Agents** complete **41.7% (35/84)** and silently drop off-screen rows on **28.6% (24/84)** of trials.
   - **Unassisted Playwright Scripts** complete **71.4% (60/84)** with an **11.9% (10/84)** silent row-truncation rate.
   - **Level Browser Playbooks** achieve **100.0% (84/84)** completion and **0.0%** silent row truncation in 19.4s per portal.

---

## Dataset Tables

| Table / Config | Rows | Description | Canonical Page |
|---|---|---|---|
| `leaderboard` | 58 | 58 live AI model and Level Playbook runs across 924 core SMB close checks & 5,923 full-vault RLVR checks | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `task_capabilities` | 13 | 13 bookkeeping, accrual-close, CFO, and browser-use task capability breakdowns | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `cli_harness_benchmark` | 6 | 6 receipt-verified multi-file CLI runs evaluated across 16 close checks | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `browser_use_regimes` | 3 | 3 browser automation regimes across 14 portals x 6 reliability gates (84 trials) | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `browser_use_gates` | 6 | 6 browser reliability gates across 14 accounting, payroll & field-service portals | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `ai_error_taxonomy` | 36 | 36 Common SMB AI Accounting, Fractional CFO & COO Mistakes across 95 close guardrails | [36 AI Accounting Mistakes](https://levelcfo.com/benchmarks/agentic-accounting/ai-error-taxonomy/) |
| `smb_case_worlds` | 40 | 40 Anonymized Real-World SMB Client Close Case Studies (84 tasks, 588 binary rubric checks) | [40 SMB Close Case Studies](https://levelcfo.com/benchmarks/agentic-accounting/smb-case-worlds/) |
| `workflows` | 12 | 12 SMB QuickBooks takeover, accrual-gap, and CFO workflows (100 binary checks) | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `evaluation_dimensions` | 5 | 5 core evaluation dimensions (Exact Math, Real Accrual Cutoffs, Hold & Ask, Subledger Matching, Board Deck Governance) | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `companyco_entities` | 4 | 4 anonymized SMB QuickBooks takeover entities with chart of accounts and onboarding handover memos | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |

---

## 40 Anonymized SMB Close Case Workbooks (`.xlsx`) & 84 Test-Case Rubrics (`cases/`)

In addition to the 10 tabular JSON/CSV/Parquet benchmark tables above, this repository includes **40 Anonymized Real-World SMB Client Close Case Studies** in `cases/` (selected from Level's 374-world / 5,923-check RLVR vault):
- **`cases/world_101_roast_co/` through `cases/world_474_.../`**: 41 multi-sheet Excel close workbooks (`.xlsx`), CSV subledger exports, and bookkeeper handover memos covering multi-entity coffee roasters, commercial roofing BuildOps-to-QBO margin bridges, AIA G702/G703 retainage & POC cutoffs, B2B SaaS ASC 606/340-40 contracts & commissions, Section 301 tariffs & FOB transit, multi-site dental ASC 842 leases, S-Corp basis, Profit First sweeps, Form 8974 R&D payroll tax credits, NY/NJ sales-tax portals, and statement continuity audits.
- **`cases/tasks/customer_world_101_task_a.json` through `customer_world_474_task_b.json`**: 84 structured AI accounting test-case prompts, input file manifests, and binary grading rubrics (588 total rubric checks).

---

## Related Level Benchmark Surfaces

- **[The Level Index Hub](https://levelcfo.com/benchmarks/)**: Central directory of Level's SMB and contractor financial benchmarks.
- **[Contractor Financial & Operating Benchmarks](https://levelcfo.com/benchmarks/contractor/)**: 19 canonical contractor metrics across 2,200+ contractors.
- **[Contractor Field Software Comparison](https://levelcfo.com/benchmarks/contractor-software-comparison/)**: Field-to-accounting evaluation across ServiceTitan, BuildOps, Housecall Pro, Jobber, Joblogic, FieldEdge, SubBase, and Kojo ([HF Dataset](https://huggingface.co/datasets/LevelCFO/software-benchmarks) · [GitHub](https://github.com/levelcfo/software-benchmarks)).
- **[Multi-Industry Accounting & Finance Software Benchmark](https://levelcfo.com/benchmarks/finance-software/)**: 9 accounting ledgers, 11 subledger handoff traps, and 6 industry close stacks ([HF Space](https://huggingface.co/spaces/LevelCFO/software-benchmarks)).
- **[Level Open Finance (v0.2.1)](https://levelcfo.com/finance-systems/)**: 20 public finance skills and local MCP server ([GitHub](https://github.com/levelcfo/open-finance-skills)).
- **[Multi-Vertical SMB Financial Benchmarks](https://huggingface.co/datasets/LevelCFO/smb-financial-benchmarks)**: Healthcare, Restaurants, Cleaning, Staffing, Landscaping, Ecommerce, Public Comps, and Valuation Multiples ([GitHub](https://github.com/levelcfo/smb-financial-benchmarks)).

---

## License, Commercial Restrictions & IP Canary Notice

- **License**: **Level Personal, Academic & Non-Commercial Evaluation License v1.0 (Commercial Use Requires License from sam@levelcfo.com)** ([full text](https://levelcfo.com/data/benchmarks/cases/LICENSE_AND_IP_NOTICE.txt))
- **Copyright Owner**: OpsPro AI, Inc. d/b/a Level ([https://levelcfo.com](https://levelcfo.com))
- **Permitted Non-Commercial Use**: Free for personal operator review, individual CPA/CFO inspection, and non-commercial academic evaluation only, with attribution and link to [https://levelcfo.com/benchmarks/agentic-accounting/](https://levelcfo.com/benchmarks/agentic-accounting/).
- **Commercial Restriction**: Commercial AI labs, foundation model trainers, RL environment builders, data brokers, and commercial software vendors are **strictly prohibited** from training on, fine-tuning on, redistributing, or commercially benchmarking with these datasets, rubrics, or case studies without a written commercial license from **sam@levelcfo.com**.
- **Commercial Licensing & Expanded Vault Contact**: **sam@levelcfo.com**
- **IP Canary Watermark Token**: `LEVEL-IP-CANARY-9F4A-7C2E-PERSONAL-USE-ONLY-CONTACT-SAM-AT-LEVELCFO-COM`

## Citation

```bibtex
@misc{levelbench_100_2026,
  title  = {LevelBench-100 (v5.0): AI Accounting, Fractional CFO & Operations Benchmark + 40 Anonymized SMB Client Close Case Studies},
  author = {Yang, Sam and Goldsmith, Lewis and Level},
  year   = {2026},
  url    = {https://levelcfo.com/benchmarks/agentic-accounting/},
  note   = {Level Personal, Academic & Non-Commercial Evaluation License v1.0. Commercial use requires license from sam@levelcfo.com}
}
```
