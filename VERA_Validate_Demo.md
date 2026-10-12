# VERA Validate: Demo Output

**Capability:** VERA Validate, exception detection and pre-boarding QC

**Task:** Compare a loan's entered data against its source documents and flag discrepancies before boarding.

All data in this demo is fully synthetic. Source documents are in `/demo-documents`. This is a demonstration of a prototype, not a production result.

## Test 1: Clean loan (control test)

A loan with no discrepancies, run first on purpose. All seven fields matched the source.

**Verdict:** CLEAR TO BOARD

**Purpose:** A validation tool that flags everything is not useful. This control test shows VERA did not raise a false alarm on a clean loan.

## Test 2: Document formats, terms match

**Input:** A synthetic Fannie Mae investor approval letter (prose format) and a synthetic internal underwriting worksheet (table format) for the same loan.

VERA extracted terms from both, cited each source line, and confirmed they matched. This included recognizing that "three and seven-eighths percent" equals "3.875%" across two different formats.

**Verdict:** CLEAR

**Purpose:** Shows VERA can read different document formats and match meaning, not just text.

## Test 3: Planted errors

Same loan, but the worksheet contained four planted transposition and entry errors.

| Field | Investor letter (source of truth) | Worksheet | Result |
|---|---|---|---|
| Interest rate | 3.875% | 3.785% | FAIL |
| Total trial payment | $1,913.82 | $1,931.82 | FAIL ($18.00 higher) |
| First payment due | 09/01/2026 | 09/15/2026 | FAIL |
| Payment due date | 1st of month | 15th of month | FAIL |
| UPB | $284,915.44 | $284,951.44 | FAIL ($36.00 higher) |

**Verdict:** HOLD, EXCEPTIONS FOUND

VERA caught every planted error and calculated the exact dollar difference on the financial fields. It also carried the due-date error through to flag the recurring due date. Four planted errors produced five failures because one error correctly carried through.

**Purpose:** Shows VERA can catch transposition errors that can lead to misapplied payments, wrong due dates, and incorrect balances.

## Note on conflicting values within one document

The worksheet's commentary paragraph restates the correct figures, while its table shows the transposed ones. VERA does not resolve this by majority or by proximity. The source-of-truth hierarchy is a written rule, so the investor approval letter governs regardless of what appears elsewhere in the file.
