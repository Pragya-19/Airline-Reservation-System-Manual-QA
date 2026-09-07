# Airline Reservation System – Test Plan

## 1. Purpose

This Test Plan defines the testing approach for the **Airline Reservation System Manual QA Portfolio Project**.

The objective is to validate major airline/travel reservation workflows and demonstrate practical QA activities including requirement analysis, test design, execution planning, defect management, traceability, exploratory testing, regression testing, and reporting.

> This is an independent QA portfolio/testing simulation and is not associated with any airline or commercial travel organization.

---

## 2. Project Scope

The project covers the following functional areas:

- Flight Search
- Flight Availability
- Fare Validation
- Passenger Details
- Ancillary Services
- Payment
- Booking Confirmation
- PNR Generation
- Ticketing
- Manage Booking
- Cancellation
- Refund

---

## 3. In-Scope Testing

The following testing activities are included:

- Functional Testing
- Positive Testing
- Negative Testing
- Boundary Value Testing
- Business Rule Testing
- UI Validation
- End-to-End Testing
- Smoke Testing
- Sanity Testing
- Retesting
- Regression Testing
- Exploratory Testing
- Risk-Based Testing
- Requirement Traceability
- Defect Reporting

---

## 4. Out of Scope

The following areas are not part of the hands-on scope of this project:

- Performance / Load Testing
- Security Penetration Testing
- Mobile Application Testing
- Production payment transactions
- Production airline inventory validation
- Real financial refund processing
- Real GDS backend validation
- Accessibility certification
- Production database modification

Where certain failure conditions cannot be reproduced safely on the selected demo application, they may be documented as **design-level test scenarios** rather than falsely marked as executed.

---

## 5. Test Objectives

The main testing objectives are to verify that:

- Users can search flights using valid criteria.
- Invalid search combinations are handled correctly.
- Flight results correspond to selected search criteria.
- Fare calculations are correct and consistent.
- Passenger information is validated appropriately.
- Payment workflows behave safely for success and failure cases.
- Duplicate payment and booking risks are handled appropriately.
- Successful booking generates a valid booking record and PNR.
- Booking information remains consistent throughout the workflow.
- Eligible bookings can be cancelled correctly.
- Refund-related states and calculations follow defined requirements.
- High-risk failures do not leave the customer in an inconsistent booking/payment state.

---

## 6. Test Approach

### 6.1 Requirement Analysis

Functional requirements are reviewed and mapped to test scenarios.

Each requirement is assigned a unique Requirement ID.

Example:

```text
REQ-FS-001
→ TS_FS_001
→ TC_FS_001
```

Traceability is maintained through the RTM.

---

### 6.2 Test Scenario Design

Test scenarios are created using:

- Positive flows
- Negative flows
- Boundary conditions
- Business rules
- Error conditions
- High-risk integration scenarios
- End-to-end user journeys

---

### 6.3 Test Case Design

Each detailed test case contains:

- Test Case ID
- Requirement ID
- Scenario ID
- Module
- Title
- Preconditions
- Test Data
- Steps
- Expected Result
- Priority
- Test Type
- Execution Status
- Actual Result
- Defect ID
- Evidence

---

## 7. Test Design Techniques

The following test design techniques are used where applicable:

### Equivalence Partitioning

Inputs are divided into valid and invalid groups.

Example:

```text
Travel Date

Valid:
Current / future supported date

Invalid:
Past date
```

### Boundary Value Analysis

Values around supported limits are tested.

Examples:

- Passenger name length
- Passenger count
- Date boundaries
- Numeric fare values

### Decision / Business Rule Testing

Business combinations are validated.

Example:

```text
Adult = 0
Infant = 1
Expected → Invalid combination
```

### Error Guessing

Testing is also performed using likely user and system failure conditions such as:

- Double-clicking Pay
- Browser refresh during payment
- Missing passenger information
- Payment timeout
- Duplicate passenger details
- Invalid booking reference

---

## 8. Test Prioritization

Testing follows a risk-based approach.

### Critical Priority

- Payment
- Duplicate payment prevention
- Booking creation
- PNR generation
- Payment amount correctness
- Payment success but booking failure

### High Priority

- Flight Search
- Fare calculation
- Passenger validation
- Booking retrieval
- Cancellation
- Refund calculations

### Medium Priority

- Boundary validations
- Non-critical UI validation
- Secondary business rules

### Low Priority

- Cosmetic issues
- Minor visual inconsistencies that do not impact booking flow

---

## 9. Smoke Testing

Smoke testing verifies whether the build/application is stable enough for further testing.

High-level smoke areas include:

```text
Application accessible
        ↓
Flight Search works
        ↓
Results page loads
        ↓
Flight/Fare can be selected
        ↓
Passenger flow accessible
        ↓
Booking/payment flow accessible
```

If a critical smoke test fails, deeper regression may be deferred until the blocker is resolved.

---

## 10. Regression Testing

Regression testing is performed around:

- Recently changed functionality
- Defect fixes
- Flight Search
- Fare calculations
- Passenger rules
- Payment
- Booking / PNR
- Cancellation
- Refund

When execution time is limited, regression is prioritized based on business impact and change risk.

---

## 11. Retesting

Retesting is performed after a defect is fixed.

The exact failed scenario is executed again using the same or equivalent test conditions to verify that the defect is resolved.

Retesting and regression are treated separately:

```text
Retesting
→ Did the exact defect fix work?

Regression
→ Did the change break existing functionality?
```

---

## 12. Exploratory Testing

Exploratory testing will be performed for high-risk and user-sensitive areas.

Example exploratory charters include:

### Flight Search Charter

Explore unusual combinations of:

- Origin
- Destination
- Dates
- Passenger counts
- Browser navigation

### Payment Charter

Explore:

- Multiple clicks
- Refresh
- Back navigation
- Timeout behavior
- Retry behavior
- Duplicate transaction risk

### Passenger Charter

Explore:

- Long names
- Special characters
- Blank fields
- Duplicate details
- Different passenger types

---

## 13. High-Risk Scenario

### Payment Successful but PNR Not Generated

This is considered a high-risk integration and business-flow scenario.

Expected QA investigation includes:

- Payment transaction status
- Transaction ID
- Booking ID
- Correlation / Request ID
- Payment API response
- Booking API response
- PNR generation status
- Timestamp
- Retry behavior
- Reversal / refund behavior
- Duplicate transaction risk

The objective is to ensure that a customer is not permanently charged without a valid booking or appropriate recovery mechanism.

---

## 14. Idempotency Validation

Payment and booking retries should not create duplicate side effects.

Example:

```text
Payment request
      ↓
Timeout
      ↓
User retries
      ↓
Same request / transaction identified
      ↓
No duplicate payment
No duplicate booking
```

Idempotency is particularly important for:

- Payment retries
- Network timeouts
- Repeated POST requests
- Double-click scenarios

---

## 15. Test Environment

Testing may be performed using a publicly available travel booking demo system where supported.

Typical environment:

```text
Platform: Web Application
Browser: Google Chrome
Operating System: Windows
Environment: Demo / Test
Network: Standard Internet Connection
```

Actual execution evidence should reflect the environment used during testing.

---

## 16. Test Data

Test data may include:

- Valid origin and destination
- Invalid same-city combinations
- Future travel dates
- Past travel dates
- Adult / Child / Infant combinations
- Passenger names
- Valid and invalid field values
- Test-mode payment data
- Booking reference / PNR data

Sensitive or real financial credentials must not be stored in the repository.

---

## 17. Defect Management

Each defect should contain:

- Defect ID
- Defect Title
- Module
- Environment
- Preconditions
- Steps to Reproduce
- Expected Result
- Actual Result
- Severity
- Priority
- Evidence
- Status

---

## 18. Severity Classification

### Critical

Application or core business flow is unusable, or there is serious financial/data impact.

Example:

```text
Customer charged multiple times because of one payment request.
```

### High

Major functionality is broken with significant business impact.

Example:

```text
Payment succeeds but booking/PNR is not generated.
```

### Medium

Functionality is affected but a workaround may exist or impact is limited.

### Low

Minor usability or cosmetic issue with little business impact.

---

## 19. Priority Classification

### High

Should be fixed urgently because it affects important business/user workflows.

### Medium

Should be fixed but does not immediately block the major workflow.

### Low

Can be scheduled later without major business impact.

> Severity represents impact. Priority represents urgency.

---

## 20. Entry Criteria

Testing can begin when:

- Requirements are available.
- Test scenarios are prepared.
- Test cases are prepared.
- Test environment is accessible.
- Required test data is available.
- Application build/demo is available for testing.

---

## 21. Exit Criteria

Testing may be considered complete for the portfolio version when:

- Planned critical and high-priority cases have been executed where supported.
- Critical defects have been documented.
- Actual execution status has been recorded.
- Defect evidence is available where defects were observed.
- RTM has been updated.
- Exploratory testing has been documented.
- Test Summary Report has been prepared.
- Known limitations and unexecuted design-level cases are documented.

---

## 22. Test Deliverables

The project deliverables include:

```text
Requirements.md
Test_Plan.md
Domain_Overview.md
Test_Scenarios.md
Test_Cases.xlsx
RTM.xlsx
Defect_Report.xlsx
Exploratory_Testing.md
User_Stories.md
Sprint_Backlog.md
Test_Summary_Report.md
Screenshots / Evidence
README.md
```

---

## 23. Risks and Mitigation

| Risk | Mitigation |
|---|---|
| Demo application may change | Record test date/environment and update cases when needed |
| Some payment failures cannot be reproduced | Maintain them as design-level scenarios |
| Real booking/payment actions are unavailable | Use test/sandbox flows only |
| Demo inventory may be limited | Use supported routes/test data |
| External service dependencies may fail | Record dependency and execution limitation |
| Limited execution time | Apply risk-based prioritization |

---

## 24. Test Completion Reporting

At project completion, the Test Summary Report will include:

- Total planned test cases
- Executed test cases
- Passed
- Failed
- Blocked
- Not Executed
- Defects by severity
- Critical observations
- Known limitations
- Residual risks
- Final QA assessment

---

## 25. Conclusion

This Test Plan provides a structured manual QA approach for validating an airline reservation workflow.

The project emphasizes practical QA skills including test design, risk analysis, defect investigation, requirement traceability, end-to-end testing, and clear reporting while maintaining an explicit distinction between **actually executed tests** and **design-level portfolio scenarios**.
