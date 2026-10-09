# VERA: AI Validation and Exception Management for Mortgage Servicing

**Catch the exception before it becomes the problem.**

VERA is an independent prototype that checks mortgage-servicing data against its source documents, flags discrepancies, and routes exceptions to a person for review before errors reach downstream systems or borrowers.

Built independently from six years of mortgage-servicing experience. All demos use synthetic data. VERA is a demonstration project, not a production system.

## See VERA in action

The example below shows VERA catching planted data-entry errors, calculating the exact differences, and placing the record on HOLD for human review.

![VERA catching errors](vera-validate-hold.png)

## Two engines, one platform

### VERA Validate: exception detection and pre-boarding QC

Checks entered servicing data against its source documents before the record moves downstream.

- Reads approval letters and underwriting worksheets
- Compares entered terms against the source of truth
- Detects mismatched dates, rates, balances, payments, and terms
- Calculates the exact difference for each mismatch
- Applies deterministic validation rules
- Returns a CLEAR or HOLD result
- Routes exceptions for human review
- In testing on 100+ synthetic records, validation took about 7 seconds per loan, compared with about 15 minutes of manual review (up to 35 minutes for complex loans)

[View the VERA Validate demo](VERA_Validate_Demo.md)

### VERA Build: repayment-plan data preparation

Turns dense prior-servicer transfer data into structured repayment-plan information.

- Reads fixed-width transfer reports
- Extracts plan balances, payment amounts, dates, and payment counts
- Builds structured payment schedules
- Validates the calculations
- Flags judgment items for human review
- Projected savings of 120+ labor hours per 150-plan batch, estimated from manual processing times (a projection, not a production result)

[View the VERA Build demo](VERA_Build_Demo.md)

## Why VERA matters

Bad servicing data can cause:

- Incorrect payment terms
- Misapplied payments
- Boarding errors
- Customer escalations
- Rework
- Compliance exposure

VERA moves validation upstream, so teams can find exceptions before errors reach downstream systems or borrowers.

## How VERA works

VERA was prototyped with Microsoft Copilot and a structured validation framework based on six years of mortgage-servicing operations.

The framework includes:

- A source-of-truth hierarchy
- Field-level validation rules
- Deterministic guardrails
- Exception handling
- Human-review routing
- Explainable results
- Audit-ready comments

VERA does not make unsupported assumptions. When information is missing, unclear, or conflicting, it flags the record for review.

## Included demos

The repository includes examples showing:

1. A clean record receiving a CLEAR result
2. Matching terms across different document formats
3. Planted errors receiving a HOLD result
4. The exact differences identified for each exception

Screenshots: `vera-validate-match.png`, `vera-validate-clear.png`, `vera-validate-hold.png`, `vera-validate-verdict.png`

## About the creator

Mary Bielma is a mortgage-servicing operations professional with 6 years of experience in servicing transfers, loan boarding, loss mitigation, bankruptcy, default servicing, and exception management. She completed MIT Sloan Executive Education programs in Artificial Intelligence: Implications for Business Strategy and Machine Learning in Business (MIT Sloan and MIT CSAIL).

**I know where servicing breaks. I use AI to help catch it.**

## Project status

VERA is an independent, evolving demonstration project.

Planned improvements:

- Additional servicing workflow types
- Excel workbook validation
- Batch processing
- Summary exception reports
- Confidence indicators
- Expanded audit documentation

## Data and intellectual property notice

Every document, record, name, number, balance, and date in this repository is synthetic. No borrower data, employer data, confidential information, proprietary system information, or company intellectual property is included. VERA was built independently for demonstration and professional portfolio purposes.
