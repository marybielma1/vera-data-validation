# VERA Build: Demo Output

**Part:** VERA Build, repayment-plan data preparation

**Input:** A synthetic prior-servicer transfer report (S2MR format) listing multiple loans.

**Task:** Extract a structured repayment plan for loan 0080012301, ready for human review before boarding.

All data in this demo is fully synthetic. No borrower, employer, or proprietary data is used. See /demo-documents/DEMO_S2MR_Transfer_Report.pdf for the input. This is a demonstration of a prototype, not a production result.

## Result: structured repayment plan for loan 0080012301

| Field | Value | Source |
|---|---|---|
| Loan number | 0080012301 | Header line |
| Plan type | 26 (Repayment plan) | "26 REPAYMENT PLAN" |
| Principal balance | $97,214.40 | "PRINCIPAL BALANCE 97,214.40" |
| Plan create date | 08/22/25 | "A 08/22/25" |
| Total repay amount | $6,842.40 | "REPAY TOTAL 6,842.40" |
| Number of payments | 6 | "CNT 6" |
| Monthly payment | $1,140.40 | Every due-amount line |

## Payment schedule

| # | Due date | Amount |
|---|---|---|
| 1 | 09/01/25 | $1,140.40 |
| 2 | 10/01/25 | $1,140.40 |
| 3 | 11/01/25 | $1,140.40 |
| 4 | 12/01/25 | $1,140.40 |
| 5 | 01/01/26 | $1,140.40 |
| 6 | 02/01/26 | $1,140.40 |

**Check:** 6 payments × $1,140.40 = $6,842.40, which matches the repay total in the report.

## Flagged for human review

1. **First payment received date vs. scheduled due date.** Received 09/10/25, scheduled 09/01/25. This is a normal late payment, but a person should confirm which date should board.
2. **Prior completed modification present.** A prior non-HAMP modification exists. Confirm this repayment plan is the active workout.
3. **Arrears ledger not shown.** Confirm the arrears detail matches the $6,842.40 total before boarding.

## Why this matters

A simple extraction tool would just copy the numbers. VERA Build also flags items a senior associate would want to check before boarding: the received-vs-due date difference, the prior modification, and the missing arrears detail. A person makes the final call.
