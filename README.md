# VERA — AI-Assisted Validation & Exception Management for Mortgage Servicing

**Catch the exception before it becomes the problem.**

VERA validates mortgage-servicing data across operational handoffs, detects discrepancies, applies deterministic rules, and routes exceptions for human review before errors reach downstream systems or borrowers.

Built independently from six years of mortgage-servicing experience. All public demos use synthetic data.

## See VERA in Action

The example below shows VERA detecting planted data-entry errors, calculating the exact differences, and placing the record on HOLD for human review.

![VERA catching errors](vera-validate-hold.png)

---

## Two Modules

### VERA Validate — Exception Detection & Pre-Boarding QC

Checks entered servicing data against its source documents before the record moves downstream.

- Reads approval letters and underwriting worksheets
- Compares entered terms against the source of truth
- Normalizes values across formats, recognizing that "three and seven-eighths percent" and "3.875%" are the same value
- Detects mismatched dates, rates, balances, payments, and terms
- Calculates exact dollar differences on every exception
- Applies deterministic validation rules
- Produces CLEAR or HOLD outcomes
- Routes exceptions for human review
- Demonstrated validation in about 7 seconds per loan versus about 15 minutes of manual review, measured on synthetic test loans
- 100+ synthetic test records at 100% accuracy, including a clean-record control test confirming zero false positives

[View the VERA Validate demo](VERA_Validate_Demo.md)

---

### VERA Build — Repayment-Plan Data Preparation

Turns dense prior-servicer transfer data into structured repayment-plan information.

- Reads fixed-width transfer reports
- Extracts plan balances, payment amounts, dates, and payment counts
- Builds structured payment schedules
- Validates calculations
- Flags judgment items for human review, including received-versus-scheduled payment dates, prior completed modifications, and missing arrears detail

[View the VERA Build demo](VERA_Build_Demo.md)

---

## Why VERA Matters

Bad servicing data can create:

- Incorrect payment terms
- Misapplied payments
- Boarding errors
- Customer escalations
- Rework
- Compliance exposure

VERA moves validation upstream so teams can find exceptions before errors reach downstream systems or borrowers.

---

## How VERA Works

VERA is a prompt-engineered validation workflow prototyped using Microsoft Copilot.

Copilot is the engine. The rules are mine. I authored the source-of-truth hierarchy, the field-level match logic, the value normalization, the exception routing, and the hold and clear decisions. I built it on my own laptop, on my own time, using synthetic documents I created to match the formats I worked in for six years.

The framework includes:

- Source-of-truth hierarchy
- Field-level validation rules
- Deterministic guardrails
- Exception handling
- Human-review routing
- Explainable results
- Audit-ready comments

VERA does not make unsupported assumptions. When information is missing, unclear, or conflicting, it flags the record for review.

---

## VERA Validate Demonstration

The repository includes examples showing:

1. A clean record receiving a CLEAR result
2. Matching terms across different document formats
3. Planted errors receiving a HOLD result
4. Exact differences identified for each exception

Included screenshots:

- `vera-validate-match.png`
- `vera-validate-clear.png`
- `vera-validate-hold.png`
- `vera-validate-verdict.png`

---

## About the Creator

Mary Bielma is a mortgage-servicing operations professional with 6+ years of experience across:

- Servicing transfers and acquisition loan boarding
- Cross-system data mapping
- Loss mitigation
- Bankruptcy
- Default servicing
- Exception management
- Compliance
- Quality assurance
- Process improvement

She spent four years boarding inbound transfer batches, roughly three per month, ranging from 10 to 525 loans each, mapping prior-servicer data into LSAMS, CMOD, and IAssist.

She completed MIT Sloan Executive Education programs in:

- Artificial Intelligence: Implications for Business Strategy, Certificate, May 2026
- Machine Learning in Business, MIT Sloan and MIT CSAIL, Completed July 2026

VERA reflects the combination of mortgage-servicing expertise, AI, automation, operational controls, and exception management.

**I know where servicing breaks. I use AI to fix it.**

---

## Project Status

VERA is an independent, evolving demonstration project.

Planned improvements include:

- Additional servicing workflow types
- Excel workbook validation
- Batch processing
- Summary exception reports
- Confidence indicators
- Expanded audit documentation

---

## Data and Intellectual Property Notice

Every document, record, name, number, balance, and date used in this repository is synthetic.

No borrower data, employer data, confidential information, proprietary system information, or company intellectual property is included.

VERA was built independently for demonstration and professional portfolio purposes.
