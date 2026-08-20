# VERA — AI-Assisted Validation & Exception Management for Mortgage Servicing

**Catch the exception before it becomes the problem.**

VERA is an independent, evolving AI-assisted validation and exception-management demonstration project for mortgage servicing. Using synthetic data and a structured validation framework, VERA compares defined servicing data with source documents, applies deterministic validation checks, calculates discrepancies, and routes exceptions for qualified human review.

> **Scope and limitations:** VERA is not a production system and does not make autonomous servicing, compliance, credit, underwriting, or borrower-impacting decisions. All public demonstrations use synthetic data. No borrower data, employer data, confidential information, proprietary system information, or company intellectual property is included.

## See VERA in Action

The example below shows VERA detecting planted data-entry discrepancies, calculating the exact differences, and placing the record on HOLD for human review.

![VERA detection example](vera-validate-hold.png)

---

## Two Capabilities

### VERA Validate — Exception Detection & Pre-Boarding QC

VERA Validate compares entered servicing data with its source documents before the record moves downstream.

- Reads approval letters and underwriting worksheets
- Compares entered terms against the defined source of truth
- Identifies mismatched dates, rates, balances, payments, and terms
- Calculates defined differences
- Applies deterministic validation rules
- Produces CLEAR or HOLD outcomes
- Routes exceptions for human review
- Demonstrated review in about 7 seconds per loan versus 15–35 minutes of manual review

[View the VERA Validate demo](VERA_Validate_Demo.md)

---

### VERA Build — Repayment-Plan Data Preparation

VERA Build converts dense prior-servicer transfer data into structured repayment-plan information for human review.

- Reads fixed-width transfer reports
- Extracts plan balances, payment amounts, dates, and payment counts
- Builds structured payment schedules
- Performs defined calculation checks
- Flags judgment items for human review
- Demonstrated potential to save 120+ labor hours per 150-plan batch

[View the VERA Build demo](VERA_Build_Demo.md)

---

## Why VERA Matters

Mortgage-servicing data discrepancies can create:

- Incorrect payment terms
- Misapplied payments
- Boarding errors
- Customer escalations
- Rework
- Compliance exposure

VERA is designed to move validation upstream so qualified reviewers can identify potential exceptions before downstream processing or borrower impact.

---

## How VERA Works

VERA was prototyped using Microsoft Copilot and a structured validation framework informed by six years of mortgage-servicing operations experience.

The framework includes:

- Source-of-truth hierarchy
- Field-level validation rules
- Deterministic guardrails
- Exception handling
- Human-review routing
- Explainable results
- Audit-ready comments

When information is missing, unclear, or conflicting, VERA flags the record for human review rather than making an unsupported assumption.

---

## Demonstration Examples

The repository includes synthetic examples showing:

1. A clean record receiving a CLEAR result
2. Matching terms across different document formats
3. Planted discrepancies receiving a HOLD result
4. Defined differences identified for each exception

Included screenshots:

- `vera-validate-match.png`
- `vera-validate-clear.png`
- `vera-validate-hold.png`
- `vera-validate-verdict.png`

---

## About the Creator

Mary Bielma is a mortgage-servicing operations and controls professional with 6+ years of experience across:

- Servicing transfers
- Loan boarding
- Loss mitigation
- Bankruptcy
- Default servicing
- Exception management
- Compliance
- Quality assurance
- Process improvement

Mary completed MIT Sloan Executive Education's **Artificial Intelligence: Implications for Business Strategy** program. She also completed **Machine Learning in Business**, offered through MIT Sloan and MIT CSAIL.

VERA reflects the combination of mortgage-servicing expertise, AI-assisted workflows, operational controls, data validation, and exception management.

**I know where servicing breaks. I use AI to help fix it.**

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

VERA was built independently for demonstration and professional-portfolio purposes. No borrower data, employer data, confidential information, proprietary system information, or company intellectual property is included.
