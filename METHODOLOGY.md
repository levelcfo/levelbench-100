# LevelBench-100: Evaluation Methodology, Dataset Provenance & Reproducibility

## 1. Benchmark Architecture & Dataset Provenance
`LevelBench-100` (`v4.1`) evaluates autonomous LLM agents across **100 real-world accounting, tax, treasury, and multi-system month-end close tasks** modeled on four synthetic-but-realistic multi-entity environments (`CompanyCo`):
1. **Commercial Mechanical & Field-Service Contractor**: Multi-week progress billing, retainage, WIP over/under-billing, field timesheet-to-payroll reconciliation, and job-level gross margin accounting.
2. **Omnichannel Ecommerce & Specialty Roaster**: Payout clearing accounts (Stripe/Shopify to bank), inventory COGS lot tracking, returns/chargebacks, and multi-state sales tax nexus.
3. **B2B Wholesale Distributor**: Three-way PO/receipt/invoice matching, vendor rebate accruals, and aging reserve schedules.
4. **Multi-Clinic Healthcare Group (MSO/PC)**: Payor contractual allowance adjustments, date-of-service vs. cash-posting cutoffs, and intercompany management-fee eliminations.

**Zero PII Guarantee**: Every general ledger transaction, bank statement PDF/CSV, payroll register, and subledger export in `data/` is 100% synthetic and deterministically generated from parameterized accounting invariants seeded by anonymized error distributions observed across 2,235 SMB financial statement audits.

---

## 2. Deterministic 4-Gate Grading Harness & Scoring Formula
Unlike open-ended LLM-as-a-judge benchmarks, `LevelBench-100` grades every model run using a **100% deterministic programmatic harness** across four binary/continuous verification gates:
1. **Gate 1 — Double-Entry & Trial-Balance Footing ($G_1 \in \{0,1\}$)**: Total debits must equal total credits ($\sum D - \sum C = 0.00$) across every posted journal entry, and the adjusted trial balance must tie to the penny.
2. **Gate 2 — Subledger-to-General-Ledger Tie-Out ($G_2 \in [0,1]$)**: Aged AR, Aged AP, WIP schedules, payroll clearing, and bank reconciliation ending balances must match their respective GL control accounts within $\pm \$0.01$.
3. **Gate 3 — Accrual Cutoff & Period Assignment ($G_3 \in [0,1]$)**: Revenue and COGS recognition must be assigned to the correct fiscal period based on service-delivery/shipment dates rather than cash-receipt dates.
4. **Gate 4 — Zero Unverified Destructive Writes ($G_4 \in \{0,1\}$)**: Any hallucinated vendor, fabricated check number, or unapproved write over an ambiguous discrepancy (e.g., a duplicate $\$19,500$ wire without holding for exception review) zeroes the task score ($G_4 = 0$).

### Task & Composite Score Equation
For task $i \in \{1, \dots, 100\}$, the deterministic task score $S_i$ is:
$$S_i = G_{1,i} \cdot G_{4,i} \cdot \left(0.50 \cdot G_{2,i} + 0.50 \cdot G_{3,i}\right)$$
A task passes ($\text{Pass}_i = 1$) if and only if $S_i = 1.00$ (exact cent-level tie-out with zero destructive writes).

---

## 3. Reproducibility & Multi-Run Variance Protocol
- **Execution Environment**: Models are evaluated at `temperature = 0` (or minimum supported provider temperature) across **75+ full end-to-end evaluation runs** (~$\$500\text{K}$ in cumulative token compute) using identical JSON/CSV/PDF input fixtures and tool schemas.
- **Single-Source vs. Cross-System Split**:
  - **Single-Source Extraction Tasks ($N = 35$)**: Frontier models achieve **96.0% accuracy** ($\pm 1.1\%$ 95% CI across repeated runs).
  - **Multi-System Reconciliation Tasks ($N = 65$)**: Unassisted LLM agents average **63.6% accuracy** ($\pm 2.4\%$ 95% CI) with a **29.0% destructive write rate** when reconciling conflicting timestamps or partial payments across bank feeds, CRM/field software, and QuickBooks GL.
  - **Deterministic Hold-and-Ask Harness**: Wrapping the model in the 4-gate verification harness raises composite accuracy to **96.0%** with **0.0% destructive ledger writes**.

---

## 4. Independent Reproduction
All task specifications, synthetic ledger fixtures, and grading scripts are included in this repository (`data/` and `eval/`) and mirrored on Hugging Face (`LevelCFO/levelbench-100`) under the MIT License.
