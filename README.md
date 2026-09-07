</> Markdown
# Airline Reservation System – Manual QA Portfolio Project

## 📌 Project Overview

This is an independent **Manual QA portfolio project** based on an airline/travel reservation workflow.

The purpose of this project is to demonstrate end-to-end software testing activities for a booking system, including requirement analysis, test planning, test design, execution approach, defect reporting, traceability, exploratory testing, Agile artifacts, and test summary reporting.

The project focuses on the functional workflow of an airline reservation system from flight search through booking, payment, PNR generation, and cancellation/refund scenarios.

---

## 🎯 Project Objectives

The objectives of this project are to:

- Understand the airline/travel reservation domain
- Analyze functional requirements
- Design positive, negative, boundary, and business-rule test scenarios
- Create detailed test cases
- Validate end-to-end booking workflows
- Identify and document defects
- Maintain requirement traceability
- Apply risk-based testing
- Practice exploratory testing
- Simulate Agile QA activities
- Prepare test summary and execution reports

---

## 🧪 System Under Test

**System:** Travel/Airline Reservation Demo Application  
**Project Type:** Independent QA Portfolio / Testing Simulation  
**Domain:** Airline / Travel Reservation

The application is used to simulate typical airline booking workflows for testing purposes.

> Note: This is a personal QA portfolio project created for learning and demonstration purposes. It is not affiliated with any airline or travel company.

---

## ✈️ Functional Modules Covered

The project covers the following modules:

1. Flight Search
2. Flight Availability
3. Fare Selection and Validation
4. Passenger Details
5. Ancillary Services
6. Payment
7. Booking Confirmation
8. PNR Generation
9. Ticketing
10. Manage Booking
11. Cancellation
12. Refund

---

## 🔄 Airline Booking Flow

```text
Flight Search
      ↓
Availability
      ↓
Fare Selection
      ↓
Passenger Details
      ↓
Ancillary Services
      ↓
Fare Review
      ↓
Payment
      ↓
Booking Confirmation
      ↓
PNR Generation
      ↓
Ticket Issuance
      ↓
Manage Booking
      ↓
Cancellation / Refund
🧩 Testing Types Covered

This project includes:

Functional Testing
Positive Testing
Negative Testing
Boundary Value Testing
Validation Testing
UI Testing
Business Rule Testing
Regression Testing
Retesting
Smoke Testing
Sanity Testing
Exploratory Testing
Risk-Based Testing
📂 Repository Structure
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
│   ├── Test_Scenarios.xlsx
│   ├── Test_Cases.xlsx
│   └── RTM.xlsx
│
├── defects/
│   └── Defect_Report.xlsx
│
├── exploratory-testing/
│   └── Exploratory_Testing.md
│
├── agile/
│   ├── User_Stories.md
│   └── Sprint_Backlog.md
│
├── reports/
│   └── Test_Summary_Report.md
│
└── evidence/
    └── screenshots/
🔍 Sample Test Scenarios

Some of the key scenarios covered in this project include:

Verify successful flight search using valid mandatory details
Verify that origin and destination cannot be the same
Verify behavior when destination is left blank
Verify that a past departure date cannot be selected
Verify that an infant cannot be selected without an accompanying adult
Verify that search results match the selected origin and destination
Verify fare calculation including taxes and additional charges
Verify fare recalculation when passenger count changes
Verify passenger mandatory-field validations
Verify behavior for duplicate passenger details
Verify successful payment
Verify failed payment handling
Verify duplicate payment prevention
Verify payment timeout handling
Verify successful booking generates a valid PNR
Verify that PNR is not null or empty
Verify correct passenger and itinerary details are stored in the booking
Verify cancellation workflow
Verify refund workflow and booking status updates
💳 High-Risk Business Scenarios

Special focus is given to high-risk booking and payment scenarios.

Payment Successful but PNR Not Generated

This scenario validates what happens when payment succeeds but booking confirmation or PNR generation fails.

Key validations include:

Payment transaction status
Booking creation status
PNR generation status
Duplicate booking prevention
Duplicate payment prevention
Transaction ID
Booking ID
Correlation/request ID
Retry behavior
Reversal/refund behavior

This type of issue can be considered a high-severity business and integration defect because a customer may be charged without receiving a confirmed booking.

🔁 Idempotency Testing

Payment APIs and booking workflows should prevent duplicate transactions when the same request is retried.

Example risk:

Payment request sent
      ↓
Response timeout
      ↓
User clicks Pay again
      ↓
Duplicate transaction risk

Expected behavior:

Same transaction/request
      ↓
Idempotency validation
      ↓
Only one payment / one booking created
🐞 Defect Reporting

Defects are documented with the following details:

Defect ID
Defect Title
Module
Preconditions
Steps to Reproduce
Actual Result
Expected Result
Severity
Priority
Environment
Test Data
Screenshot / Evidence
Status
⚖️ Severity vs Priority

Severity refers to the impact of the defect on the system or business.

Priority refers to how urgently the defect should be fixed.

Example:

Payment deducted but booking not created
Severity: High
Priority: High
🔗 Requirement Traceability

A Requirement Traceability Matrix (RTM) is maintained to map:

Requirement
    ↓
Test Scenario
    ↓
Test Case
    ↓
Execution Result
    ↓
Defect

This helps ensure that all defined requirements are covered by testing.

🔎 Exploratory Testing

Exploratory testing is performed for areas such as:

Flight search combinations
Passenger data variations
Fare changes
Payment retries
Browser navigation
Error handling
Session behavior
Unexpected user actions

Exploratory testing combines learning, test design, execution, and investigation during the same testing session.

🏃 Agile QA Simulation

The project also includes simulated Agile QA activities such as:

User stories
Acceptance criteria
Sprint backlog
Defect triage
Retesting
Regression planning
Sprint test execution
Test summary reporting

Example user story:

As a traveler,
I want to search for available flights
so that I can select a suitable flight for my journey.

Example acceptance criteria:

Given valid search details
When the user searches for a flight
Then matching available flights should be displayed.
📊 Risk-Based Testing Approach

When execution time is limited, testing is prioritized in this order:

Smoke / build verification
Business-critical booking flows
Payment
Booking confirmation and PNR generation
Recently changed functionality
High-severity defect fixes
High-risk integrations
Regression around impacted areas
Lower-risk and cosmetic scenarios
🛠️ Tools Used
Manual Testing
Microsoft Excel / Spreadsheet-based test documentation
Git
GitHub
Browser Developer Tools
Screenshots and test evidence
🧠 Domain Concepts Covered

Key airline domain terms covered in this project include:

PNR – Passenger Name Record
PAX – Passenger
Itinerary
Flight Segment
Fare Class
Ancillary Services
SSR – Special Service Request
GDS – Global Distribution System
Booking Confirmation
Ticketing
Cancellation
Refund
Payment Reconciliation
Idempotency
📈 Future Enhancements

Future enhancements may include:

REST API testing using Postman
API automation using Python and Pytest
UI automation using Playwright with TypeScript
GitHub Actions CI/CD integration
SQL-based backend validation
Basic AI testing for an airline support chatbot
👩‍💻 About This Project

This project was created as part of my QA upskilling and portfolio development to demonstrate practical manual testing skills, domain understanding, test design techniques, defect analysis, and end-to-end quality assurance thinking.

It is intended to showcase my current hands-on QA capabilities and structured testing approach.

📌 Disclaimer

This is an independent educational and portfolio project.

It is not associated with, endorsed by, or created for any airline, travel company, booking platform, or commercial organization.
