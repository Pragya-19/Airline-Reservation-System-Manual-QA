# Airline Reservation System – Test Scenarios

## Purpose

This document contains functional, negative, boundary, and business-rule test scenarios for the Airline Reservation System Manual QA portfolio project.

The scenarios are designed against the functional requirements defined in `Requirements.md`.

> Note: This is an independent QA portfolio simulation. Actual execution results may be updated based on the behavior supported by the selected travel booking demo application.

---

# Module 1 – Flight Search

### TS_FS_001
Verify that the user can successfully search for flights using valid mandatory search criteria.

### TS_FS_002
Verify that the system prevents flight search when origin and destination are the same.

### TS_FS_003
Verify that the system prevents or appropriately handles selection of a past departure date.

### TS_FS_004
Verify that an infant passenger cannot be selected without an accompanying adult.

### TS_FS_005
Verify that the system prevents flight search when the destination field is left blank.

### TS_FS_006
Verify that flight search results match the selected origin and destination.

### TS_FS_007
Verify that flight search results correspond to the selected travel date.

### TS_FS_008
Verify the system behavior when no flights are available for the selected search criteria.

---

# Module 2 – Fare

### TS_FARE_001
Verify that the correct fare is displayed for the selected flight.

### TS_FARE_002
Verify that total fare is calculated correctly using applicable base fare, taxes, fees, and ancillary charges.

### TS_FARE_003
Verify that the total fare is recalculated correctly when passenger count changes.

### TS_FARE_004
Verify that fare is recalculated correctly when passenger type changes where applicable.

### TS_FARE_005
Verify that the fare displayed during flight selection remains consistent with the booking review page unless a fare change is communicated.

### TS_FARE_006
Verify that applicable discounts or promotional values are reflected correctly in the final fare.

### TS_FARE_007
Verify that the final payable amount displayed before payment is correct.

---

# Module 3 – Passenger Details

### TS_PAX_001
Verify that the user can enter valid passenger details successfully.

### TS_PAX_002
Verify that mandatory passenger fields cannot be left blank.

### TS_PAX_003
Verify system behavior when a passenger name exceeds the permitted field length.

### TS_PAX_004
Verify system behavior when duplicate passenger details are entered within the same booking.

### TS_PAX_005
Verify that supported passenger types such as Adult, Child, and Infant are handled correctly.

### TS_PAX_006
Verify that invalid passenger data is rejected or appropriately validated.

### TS_PAX_007
Verify that passenger details entered during booking are displayed correctly on the booking review page.

### TS_PAX_008
Verify that special characters in passenger names are handled according to supported validation rules.

---

# Module 4 – Payment

### TS_PAY_001
Verify that the user can successfully complete payment using a supported payment method.

### TS_PAY_002
Verify that a failed payment does not incorrectly create a successfully paid booking.

### TS_PAY_003
Verify that repeated payment submission does not result in duplicate charges.

### TS_PAY_004
Verify that repeated payment submission does not result in duplicate booking creation.

### TS_PAY_005
Verify system behavior when the payment request times out.

### TS_PAY_006
Verify that the amount charged matches the final payable booking amount.

### TS_PAY_007
Verify that payment status is updated correctly after a successful transaction.

### TS_PAY_008
Verify that payment status is updated correctly after a failed transaction.

### TS_PAY_009
Verify appropriate handling when payment succeeds but booking or PNR generation fails.

### TS_PAY_010
Verify that retrying a timed-out payment request does not create duplicate transaction side effects.

---

# Module 5 – Booking and PNR

### TS_PNR_001
Verify that a successful booking creates a valid booking record.

### TS_PNR_002
Verify that a successful booking generates a non-null and non-empty PNR.

### TS_PNR_003
Verify that passenger details stored in the booking are correct.

### TS_PNR_004
Verify that flight itinerary details stored in the booking are correct.

### TS_PNR_005
Verify that the fare stored in the booking matches the final payable amount.

### TS_PNR_006
Verify that payment status stored in the booking is correct.

### TS_PNR_007
Verify that a booking can be retrieved using the supported booking reference or PNR.

### TS_PNR_008
Verify that separate booking records receive appropriate booking references/PNRs according to system rules.

### TS_PNR_009
Verify that multiple passengers can be associated with the same reservation/PNR where supported.

### TS_PNR_010
Verify appropriate system handling when payment is successful but PNR generation fails.

---

# Module 6 – Cancellation

### TS_CAN_001
Verify that an eligible confirmed booking can be cancelled successfully.

### TS_CAN_002
Verify that booking status is updated correctly after successful cancellation.

### TS_CAN_003
Verify system behavior when cancellation is attempted for an ineligible booking.

### TS_CAN_004
Verify that cancelled booking details remain retrievable where supported.

### TS_CAN_005
Verify that applicable cancellation charges are calculated correctly according to booking rules.

### TS_CAN_006
Verify that repeated cancellation requests do not produce inconsistent booking states.

---

# Module 7 – Refund

### TS_REF_001
Verify that an eligible cancelled booking initiates the refund process correctly.

### TS_REF_002
Verify that the calculated refundable amount follows the applicable fare and cancellation rules.

### TS_REF_003
Verify that refund status is updated correctly during refund processing.

### TS_REF_004
Verify that a completed refund is reflected correctly against the booking.

### TS_REF_005
Verify system behavior when refund processing fails.

### TS_REF_006
Verify that duplicate refund requests do not result in duplicate refunds.

---

# High-Risk End-to-End Scenarios

### TS_E2E_001
Verify the complete successful flow from flight search through payment, booking confirmation, and PNR generation.

### TS_E2E_002
Verify that payment success followed by booking failure does not result in an unresolved customer charge.

### TS_E2E_003
Verify that retrying payment after a timeout does not result in duplicate payment or duplicate booking.

### TS_E2E_004
Verify fare consistency from flight search through final payment.

### TS_E2E_005
Verify that passenger, itinerary, fare, payment, and booking information remain consistent throughout the booking lifecycle.

---

# Test Design Coverage

The scenarios include:

- Positive Testing
- Negative Testing
- Boundary Testing
- Functional Testing
- Business Rule Testing
- Integration-oriented Testing
- Risk-Based Testing
- End-to-End Testing
