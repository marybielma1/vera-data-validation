# VERA Validate — Demo Output

**Capability:** VERA Validate — Exception Detection & Pre-Boarding QC

**Task:** Compare a loan's entered data against its source documents and flag discrepancies before boarding.

All data is fully synthetic. Source documents in `/demo-documents`.

---

## Test 1 — Clean loan (control test)

A loan with no discrepancies, run first on purpose. All seven fields matched the source. Verdict: **CLEAR TO BOARD.**

Purpose: a validation tool that flags everything is useless. This control test proves VERA does not raise false alarms on clean data. Across 100+ synthetic test records, VERA produced no false positives.

---

## Test 2 — Real document formats, terms match

Input: a Fannie Mae investor approval letter (prose format) and an internal underwriting worksheet (table format) for the same loan.

VERA extracted terms from both, cited each source line, and confirmed they matched — including correctly recognizing that "three and seven-eighths percent" equals "3.875%" across two different formats. Verdict: **CLEAR.**

Purpose: proves VERA reads real document formats and understands meaning, not just matching text.

---

## Test 3 — Real documents, planted errors

Same loan, but the worksheet contained four transposition and entry errors.

| Field | Investor Letter (truth) | Worksheet | Result |
|---|---|---|---|
| Interest rate | 3.875% | 3.785% | FAIL |
| Total trial payment | $1,913.82 | $1,931.82 | FAIL ($18.00 higher) |
| First payment due | 09/01/2026 | 09/15/2026 | FAIL |
| Payment due date | 1st of month | 15th of month | FAIL |
| UPB | $284,915.44 | $284,951.44 | FAIL ($36.00 higher) |

Verdict: **HOLD — EXCEPTIONS FOUND.**

VERA caught every error, calculated the exact dollar variance on the financial fields, and cascaded the due-date error to flag the recurring due date as well. Four planted errors produced five failures because one error correctly propagated.

Purpose: proves VERA catches the exact transposition errors that cause borrower harm — misapplied payments, wrong due dates, incorrect balances.

**Note on conflicting values within one document:** the worksheet's commentary paragraph restates the correct figures while its table shows the transposed ones. VERA does not resolve this by majority or by proximity. The source-of-truth hierarchy is a written rule, so the investor approval letter governs regardless of what appears elsewhere in the file.
