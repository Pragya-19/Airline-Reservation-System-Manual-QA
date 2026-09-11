✈️ Airline Reservation System — Manual QA Portfolio Project

<p align="center">
  <img src="https://img.shields.io/badge/Testing-Manual%20QA-2563EB?style=for-the-badge" alt="Manual QA"/>
  <img src="https://img.shields.io/badge/Domain-Airline%20%2F%20Travel-0F766E?style=for-the-badge" alt="Airline Domain"/>
  <img src="https://img.shields.io/badge/Test%20Cases-39-7C3AED?style=for-the-badge" alt="39 Test Cases"/>
  <img src="https://img.shields.io/badge/Project-Closed-15803D?style=for-the-badge" alt="Project Closed"/>
</p>

<p align="center">
  <strong>End-to-end manual QA project covering flight search, fare validation, passenger rules, payments, booking/PNR, cancellation, refund, traceability, defects, and test closure.</strong>
</p>

📌 **Project Overview**

This repository presents an independent Manual QA portfolio project for an airline/travel reservation workflow.

The project demonstrates practical QA execution across:

Requirement analysis

Test planning

Test scenario and test case design

Functional, negative, boundary and business-rule testing

Risk-based testing

End-to-end workflow validation

Defect reporting and retesting

Requirement Traceability Matrix (RTM)

Exploratory testing

Test summary and project closure

The System Under Test (SUT) is a public travel reservation demo application used only for testing and learning purposes.

📊 **Project Snapshot**

Metric

Result

Total Test Cases

39

Passed

29

Failed

4

Blocked

4

Not Executed

2

Domain

Airline / Travel Reservation

Environment

Web Demo Application, Admin Portal, Stripe Sandbox

Project Status

Closed with documented defects and test limitations

Execution integrity: Scenarios that could not be reproduced safely or deterministically were marked Blocked or Not Executed rather than being reported as passed.

🧭 **End-to-End Booking Flow**

flowchart LR
    A[Flight Search] --> B[Availability]
    B --> C[Fare Selection]
    C --> D[Passenger Details]
    D --> E[Fare Review]
    E --> F[Payment]
    F --> G[Booking Confirmation]
    G --> H[Booking / PNR Validation]
    H --> I[Manage Booking]
    I --> J[Cancellation / Refund]

    F -. High Risk .-> K[Duplicate Payment Protection]
    G -. Integration Risk .-> L[Supplier / PNR Failure Handling]
    J -. Business Risk .-> M[Refund Validation]

✅ **Functional Coverage**

Module

Coverage Highlights

Flight Search

Valid search, same origin/destination, mandatory fields, past date, no-result behavior

Fare

Fare visibility, tax/fee calculation, passenger-count recalculation, fare consistency

Passenger

Mandatory fields, name boundary, duplicate passenger data, child/infant handling

Payment

Successful payment, failed/cancelled payment, duplicate payment/booking protection, amount consistency

Booking / PNR

Booking creation, passenger/itinerary/fare validation, booking retrieval

Cancellation

Eligible cancellation, cancellation state handling, repeat-cancellation prevention

Refund

Refund amount validation and refund-state observations

End-to-End

Search → booking → payment → confirmation and fare consistency

🧪 **Test Techniques Applied**

<p>
  <img src="https://img.shields.io/badge/Positive-Testing-0EA5E9" alt="Positive Testing"/>
  <img src="https://img.shields.io/badge/Negative-Testing-E11D48" alt="Negative Testing"/>
  <img src="https://img.shields.io/badge/Boundary-Value-F59E0B" alt="Boundary Testing"/>
  <img src="https://img.shields.io/badge/Regression-Testing-8B5CF6" alt="Regression Testing"/>
  <img src="https://img.shields.io/badge/Risk--Based-Testing-DC2626" alt="Risk Based Testing"/>
  <img src="https://img.shields.io/badge/End--to--End-Testing-059669" alt="End to End Testing"/>
</p>

Additional techniques include:

Business-rule validation

Mandatory-field validation

Retesting

Exploratory testing

Integration-focused scenario design

Requirement traceability

🐞 **Representative Defects Identified**

DEF-FS-001 — Same origin and destination accepted

The application allowed a search with identical origin and destination instead of blocking the invalid route combination.

DEF-PAX-001 — Excessive passenger name silently truncated

The passenger name field accepted an excessively long value without validation and later truncated it on the invoice.

DEF-PAX-002 — Child/infant combinations returned inconsistent availability

Adult-only searches returned flights, while valid passenger combinations involving child/infant categories returned zero flights.

DEF-CAN-001 — Cancellation blocked by supplier/PNR processing issue

A cancellation request could not be completed because the Admin portal returned an invalid Sabre API response and the PNR remained unissued.

A payment gateway limit issue was also observed earlier and successfully retested later using Stripe Sandbox.

⚠️ **High-Risk Areas Covered**

The project gives additional attention to business-critical scenarios such as:

Payment amount versus final payable amount

Duplicate payment prevention

Duplicate booking prevention

Payment timeout/retry risk

Booking confirmation after payment

Booking/PNR retrieval

Supplier integration failure

Cancellation state handling

Refund calculation

Fare consistency across the booking journey

🔗 **Requirement Traceability**

The RTM maps the complete QA chain:

flowchart LR

    R[Requirement] --> S[Test Scenario]
    S --> T[Test Case]
    T --> E[Execution Result]
    E --> D[Defect / Observation]

This provides visibility into:

Requirement coverage

Execution status

Failed requirements

Blocked scenarios

Defect linkage

Known coverage gaps

📂 **Repository Artifacts**

Airline-Reservation-System-Manual-QA/
│

├── README.md
│

├── docs/

│   ├── Requirements.md

│   ├── Test_Plan.md

│   └── Domain_Overview.md
│

├── test-design/

│   ├── Test_Scenarios.md

│   ├── Test_Cases.xlsx

│   └── RTM.xlsx
│

├── defects/

│   └── Defect_Report.xlsx
│

├── reports/

│   ├── Test_Summary_Report.pdf

│   └── Project_Closure_Report.pdf
│

└── evidence/

    └── screenshots/

🛠️ **Tools Used**

Area

Tools

Test Documentation

Microsoft Excel / Spreadsheet-based documentation

Test Execution

Web Browser, Browser Developer Tools

Payment Validation

Stripe Sandbox

Version Control

Git, GitHub

Evidence

Screenshots and execution documentation

✈️ **Airline / Travel Domain Concepts Applied**

PNR · PAX · Itinerary · Flight Segment · Fare Class · GDS / Supplier Integration · Booking Confirmation · Payment Reconciliation · Cancellation · Refund · Idempotency

🚧 **Project Constraints**

Because the project uses a public demo application, some conditions were outside the tester's control, including:

Third-party supplier behavior

Demo-data availability

Sandbox-payment behavior

Inability to deterministically reproduce certain timeout/failure states

Limited control over supplier-side PNR issuance

These limitations are explicitly documented in the test cases, RTM, defect report, and test summary.

📈 **Future Enhancements**

Potential extensions:

REST API testing with Postman

API automation with Python + Pytest

UI automation with Playwright + TypeScript

SQL-based backend validation

GitHub Actions CI/CD

Basic AI/LLM testing for an airline support chatbot

📄 **Disclaimer**

This is an independent educational and QA portfolio project.

It is not affiliated with, endorsed by, or created for any airline, travel company, booking platform, payment provider, or commercial organization.
