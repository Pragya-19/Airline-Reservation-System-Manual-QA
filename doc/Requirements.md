# Airline Reservation System – Functional Requirements

## Project Scope

This document defines the functional requirements used for the Airline Reservation System Manual QA portfolio project.

The requirements are created for testing and portfolio simulation based on common airline/travel reservation workflows.

---

# Module 1 – Flight Search

## REQ-FS-001 – Valid Flight Search

The system should allow the user to search for available flights by providing valid mandatory search criteria.

Mandatory information may include:

- Origin
- Destination
- Departure Date
- Passenger Count

---

## REQ-FS-002 – Origin and Destination Validation

Origin and destination must be provided before a flight search can be performed.

Origin and destination should not be the same location.

---

## REQ-FS-003 – Departure Date Validation

The departure date should not be earlier than the current date.

The system should prevent or appropriately handle selection of an invalid past travel date.

---

## REQ-FS-004 – Passenger Validation

At least one valid passenger should be selected.

An infant should not be allowed without an accompanying adult.

---

## REQ-FS-005 – Search Results

For a valid search, the system should display available flights matching the selected search criteria.

Search results should correspond to:

- Selected Origin
- Selected Destination
- Travel Date
- Passenger Criteria

---

# Module 2 – Fare

## REQ-FARE-001 – Fare Display

The system should display the fare applicable to the selected flight.

---

## REQ-FARE-002 – Fare Calculation

The total payable fare should be calculated based on applicable:

- Base Fare
- Taxes
- Fees
- Selected Ancillary Services
- Discounts, where applicable

---

## REQ-FARE-003 – Passenger Fare Recalculation

The system should recalculate the total fare when the number or type of passengers changes.

---

## REQ-FARE-004 – Fare Consistency

The fare shown during flight selection should remain consistent through booking review and payment unless a fare change is communicated to the user.

---

# Module 3 – Passenger Details

## REQ-PAX-001 – Mandatory Passenger Information

Mandatory passenger information should be captured before booking can continue.

---

## REQ-PAX-002 – Passenger Data Validation

The system should validate passenger details based on supported field rules and restrictions.

---

## REQ-PAX-003 – Passenger Type

The system should correctly handle supported passenger categories such as:

- Adult
- Child
- Infant

---

## REQ-PAX-004 – Duplicate Passenger Details

The system should appropriately handle duplicate passenger information entered within the same reservation.

---

# Module 4 – Payment

## REQ-PAY-001 – Successful Payment

The system should allow the user to complete payment using supported payment methods.

---

## REQ-PAY-002 – Failed Payment

If payment fails, the booking should not incorrectly be marked as successfully paid.

---

## REQ-PAY-003 – Duplicate Payment Prevention

Repeated payment submission should not result in duplicate charges for the same booking.

---

## REQ-PAY-004 – Payment Timeout

The system should safely handle payment timeout scenarios without creating duplicate payment or booking records.

---

## REQ-PAY-005 – Payment Amount

The amount charged should match the final payable booking amount.

---

# Module 5 – Booking and PNR

## REQ-PNR-001 – Booking Creation

A successful booking should create a valid booking record.

---

## REQ-PNR-002 – PNR Generation

A successful booking should generate a valid non-null and non-empty PNR.

---

## REQ-PNR-003 – Booking Information

The booking record should contain the correct:

- Passenger Details
- Flight Details
- Travel Date
- Fare
- Payment Status

---

## REQ-PNR-004 – Booking Retrieval

The user should be able to retrieve the booking using the supported booking reference or PNR.

---

## REQ-PNR-005 – Payment Successful but Booking Failure

If payment succeeds but booking or PNR generation fails, the system should prevent duplicate transactions and support appropriate reconciliation, reversal, retry, or recovery handling.

---

# Module 6 – Cancellation and Refund

## REQ-CAN-001 – Booking Cancellation

An eligible confirmed booking should support cancellation according to applicable booking rules.

---

## REQ-CAN-002 – Booking Status

After successful cancellation, the booking status should be updated appropriately.

---

## REQ-REF-001 – Refund

Where a booking is eligible for refund, the correct refundable amount should be calculated according to applicable rules.

---

## REQ-REF-002 – Refund Status

The system should maintain the appropriate refund status throughout refund processing.

---

# Requirement Traceability

Each requirement in this document will be mapped to:

Requirement → Test Scenario → Test Case → Execution Result → Defect
