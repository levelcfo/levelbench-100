# LevelBench-100 (v4.1.0): AI Accounting, Fractional CFO & Operations Benchmark

> **NON-COMMERCIAL EVALUATION LICENSE NOTICE**: This dataset and benchmark suite are published under the **Level Personal, Academic & Non-Commercial Evaluation License v1.0 (Commercial Use Requires License from sam@levelcfo.com)** ([full license & IP notice](https://levelcfo.com/data/benchmarks/cases/LICENSE_AND_IP_NOTICE.txt)). Free for personal operator review, individual CPA/CFO inspection, and non-commercial academic evaluation only. **Commercial AI labs, foundation model trainers, RL environment builders, data brokers, and commercial software vendors are strictly prohibited from training on, redistributing, or commercially benchmarking with these datasets or cases without a written commercial license.** For commercial licensing, model training rights, enterprise RL environments, or access to Level's expanded vault across 2,200+ SMB cleanups, contact **sam@levelcfo.com**.

Release: **4.1.0**

- **Canonical Interactive Benchmark**: [https://levelcfo.com/benchmarks/agentic-accounting/](https://levelcfo.com/benchmarks/agentic-accounting/)
- **30 Common AI Accounting, CFO & Operations Mistakes**: [https://levelcfo.com/benchmarks/agentic-accounting/ai-error-taxonomy/](https://levelcfo.com/benchmarks/agentic-accounting/ai-error-taxonomy/)
- **15 Anonymized SMB Client Close Case Studies (.xlsx / .csv / .json)**: [https://levelcfo.com/benchmarks/agentic-accounting/smb-case-worlds/](https://levelcfo.com/benchmarks/agentic-accounting/smb-case-worlds/)
- **Full Benchmark Deep-Dive Article**: [https://levelcfo.com/blog/levelbench-100-ai-accounting-cfo-benchmark/](https://levelcfo.com/blog/levelbench-100-ai-accounting-cfo-benchmark/)
- **Hugging Face Dataset**: [https://huggingface.co/datasets/LevelCFO/levelbench-100](https://huggingface.co/datasets/LevelCFO/levelbench-100)
- **Hugging Face Leaderboard Space**: [https://huggingface.co/spaces/LevelCFO/levelbench-100](https://huggingface.co/spaces/LevelCFO/levelbench-100)
- **GitHub Repository**: [https://github.com/levelcfo/levelbench-100](https://github.com/levelcfo/levelbench-100)
- **Published by**: [Level](https://levelcfo.com) (always-on bookkeeping, month-end close, tax, and fractional CFO service for contractors, service businesses, and ecommerce brands)

---

## Executive Summary: Can AI Close Real SMB Books?

We evaluated **38 AI configurations** (27 unassisted foundation models, 4 multi-file agentic CLI harnesses, and 7 AI + Level Playbook configurations) across **100 binary checks** spanning 12 real-world SMB QuickBooks takeover, accrual-close, and fractional CFO workflows, plus **15 anonymized SMB client close case studies** (31 close tasks and 214 binary rubric checks), **30 common AI accounting error patterns** (distilled from 95 automated close guardrails), and **14 production accounting, payroll, and field-service portals** (84 portal-gate trials).

### Headline Findings

1. **Unassisted Raw Foundation Models Score 31.0% to 71.0%**:
   - **Gemini 4 Argon (Medium Thinking)** ranks #1 among unassisted raw models at **71.0%** zero-shot accuracy (**81.0%** with accounting SOP prompts, **28.6%** bad book-entry rate, 26.09s, $0.04/close).
   - **Claude Opus 5.5** ranks #2 among raw models at **69.0%** zero-shot (**80.0%** with SOP prompts), followed by **Claude Fable 5.1** (**68.0%**), **GPT-6.1 Sol High** (**67.0%**), and **GPT-6.1 Sol Medium** (**66.0%**).
   - Fast worker models alone (**Gemini 3.8 Flash** at **58.0%** and **GPT-5.6 Terra Low** at **57.0%**) and open-weight models (**DeepSeek V3** at **46.0%**, **Kimi K2.5** at **41.0%**, **Qwen 3 Next 80B** at **35.0%**, **Qwen 2.5 72B** at **31.0%**) fail on unlinked prior-bookkeeper manual Journal Entries, tied supply-house AP bills, missing check stub images, and seller-broker M&A add-backs.
2. **Multi-File Agentic CLI Harnesses Reach 76.0% to 84.0% Unassisted (100.0% When Guided by Level Checklists)**:
   - **Gemini CLI 0.64.0 (Gemini 4 Argon Medium)** scores **84.0%** raw (**89.0%** with SOP prompts), **Antigravity CLI 1.4.0** scores **83.0%** raw (**88.0%** with SOP prompts), and **Codex CLI (GPT-6.1 Sol)** scores **81.0%** raw (**87.0%** with SOP prompts).
   - On our 26-check Multi-File Close CLI Harness Benchmark, equipping **Codex CLI (GPT-5.6 Terra)** with Level's multi-file close checklist reaches **100.0% (26/26)** in 42.98s at **$0.018/close**.
3. **AI + Level Playbooks (2,200+ Past Experiences) + Operator Review Reaches 100.0% Accuracy and 0.0% Bad Book-Entry Rate**:
   - Pairing frontier or fast worker models (**GPT-5.6 Terra**, **Gemini 3.8 Flash**, **Claude Haiku 5.5**, **DeepSeek V3**) with Level's deterministic close playbooks and human controller review lifts accuracy to **100.0%** (+29.0 to +54.0 percentage-point lift) with **100.0% 3-run consistency** and **0.0% bad book entries**.
4. **14-Portal Browser-Use Benchmark (84 Portal-Gate Trials)**:
   - Across QuickBooks Online, BuildOps, ServiceTitan, Housecall Pro, LMN, Roofr, MarketSharp, Rippling, Gusto, Ramp, Brex, Settle, Finaloop, and Shopify:
   - **Unassisted Vision Browser Agents** complete **41.7% (35/84)** and silently drop off-screen rows on **28.6% (24/84)** of trials.
   - **Unassisted Playwright Scripts** complete **71.4% (60/84)** with an **11.9% (10/84)** silent row-truncation rate.
   - **Level Browser Playbooks** achieve **100.0% (84/84)** completion and **0.0%** silent row truncation in 19.4s per portal.

---

## Dataset Tables

| Table / Config | Rows | Description | Canonical Page |
|---|---|---|---|
| `leaderboard` | 38 | 38 AI models, CLI harnesses, and Level Playbook setups across 100 SMB QuickBooks takeover checks | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `task_capabilities` | 13 | 13 bookkeeping, accrual-close, CFO, and browser-use task capability breakdowns | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `cli_harness_benchmark` | 6 | 6 multi-file CLI harnesses evaluated across 26 close checks | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `browser_use_regimes` | 3 | 3 browser automation regimes across 14 portals x 6 reliability gates (84 trials) | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `browser_use_gates` | 6 | 6 browser reliability gates across 14 accounting, payroll & field-service portals | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `ai_error_taxonomy` | 30 | 30 Common SMB AI Accounting, Fractional CFO & COO Mistakes across 95 close guardrails | [30 AI Accounting Mistakes](https://levelcfo.com/benchmarks/agentic-accounting/ai-error-taxonomy/) |
| `smb_case_worlds` | 15 | 15 Anonymized Real-World SMB Client Close Case Studies (31 tasks, 214 binary rubric checks) | [15 SMB Close Case Studies](https://levelcfo.com/benchmarks/agentic-accounting/smb-case-worlds/) |
| `workflows` | 12 | 12 SMB QuickBooks takeover, accrual-gap, and CFO workflows (100 binary checks) | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `evaluation_dimensions` | 5 | 5 core evaluation dimensions (Exact Math, Real Accrual Cutoffs, Hold & Ask, Subledger Matching, Board Deck Governance) | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |
| `companyco_entities` | 4 | 4 anonymized SMB QuickBooks takeover entities with chart of accounts and onboarding handover memos | [Agentic Accounting Benchmark](https://levelcfo.com/benchmarks/agentic-accounting/) |

---

## Related Level Benchmark Surfaces

- **[The Level Index Hub](https://levelcfo.com/benchmarks/)**: Central directory of Level's SMB and contractor financial benchmarks.
- **[Contractor Financial & Operating Benchmarks](https://levelcfo.com/benchmarks/contractor/)**: 19 canonical contractor metrics across 2,200+ contractors.
- **[Contractor Field Software Comparison](https://levelcfo.com/benchmarks/contractor-software-comparison/)**: Field-to-accounting evaluation across ServiceTitan, BuildOps, Housecall Pro, Jobber, Joblogic, FieldEdge, SubBase, and Kojo ([HF Dataset](https://huggingface.co/datasets/LevelCFO/software-benchmarks) · [GitHub](https://github.com/levelcfo/software-benchmarks)).
- **[Multi-Industry Accounting & Finance Software Benchmark](https://levelcfo.com/benchmarks/finance-software/)**: 9 accounting ledgers, 11 subledger handoff traps, and 6 industry close stacks ([HF Space](https://huggingface.co/spaces/LevelCFO/software-benchmarks)).
- **[Level Open Finance (v0.2.0)](https://levelcfo.com/finance-systems/)**: 20 public finance skills and local MCP server ([GitHub](https://github.com/levelcfo/open-finance-skills)).
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
  title  = {LevelBench-100 (v4.1): AI Accounting, Fractional CFO & Operations Benchmark + 15 Anonymized SMB Client Close Case Studies},
  author = {Yang, Sam and Goldsmith, Lewis and Level},
  year   = {2026},
  url    = {https://levelcfo.com/benchmarks/agentic-accounting/},
  note   = {Level Personal, Academic & Non-Commercial Evaluation License v1.0. Commercial use requires license from sam@levelcfo.com}
}
```
