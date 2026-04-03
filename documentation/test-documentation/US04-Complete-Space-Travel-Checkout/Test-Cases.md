# Test Case Specification: Checkout & Data Persistence (US_04)

This document details the testing strategy and critical scenarios for the **Space Travel Checkout** process, integrating state transitions, session persistence, and data integrity validations.

---

## 1. Test Scenario Mapping

| Scenario ID | Test Scenario | Technique Applied | Acceptance Criteria Covered |
| :--- | :--- | :--- | :--- |
| **TC_01** | Destination Booking & State Transition | State Transition Testing | AC_1 |
| **TC_02** | Order Summary Integrity & Calculation | Session / Data Integrity | AC_1, AC_2 |
| **TC_03** | Mandatory Form Fields & Inline Validation | Negative Testing | AC_4, AC_6 |
| **TC_04** | Legal Consent (Terms & Conditions) Enforcement | Logic Testing | AC_5 |
| **TC_05** | Dynamic Destination Insights (Climate Graph) | Visual/UI Testing | AC_3 |

---

## 2. Critical Test Cases Detail

### TC_01: Destination Booking & State Transition
* **Technique:** State Transition Testing.
* **Objective:** Verify button state change and automatic redirection.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Click the **'BOOK'** button on a destination card. | Button text changes to **'BOOKED'** and a purple checkmark appears. |
| 2 | Observe system behavior. | User is automatically redirected to the **Checkout** page. |
| 3 | Verify card body interaction. | Clicking the image or text remains read-only (no action). |

### TC_02: Order Summary Integrity (Checkout)
* **Technique:** Data Integrity / Session Persistence.
* **Pre-conditions:** User has selected 2 travelers and a date range (e.g., Apr 4 - 10).

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Navigate to the Checkout page after booking. | **Order Summary** panel correctly displays 2 travelers and selected dates. |
| 2 | Verify the **Total** price calculation. | Total reflects correctly: `[Unit Price x 2 travelers]`. |

### TC_03: Mandatory Form Fields & Inline Validation
* **Technique:** Negative Testing / Input Validation.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Write something in name, delete it, leave **Name** empty and change focus. | Warning appears: **"Name is a required field"**. |
| 2 | Enter invalid SSN format (e.g., "123-AB-456"). | Warning appears: **"Enter a valid Social Security number (xxx-xx-xxxx)"**. |
| 3 | Observe **'PAY NOW'** button. | Button remains **disabled** until all fields are valid according to AC_6. |

### TC_04: Legal Consent (Terms & Conditions) Enforcement
* **Technique:** Logic Testing.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Fill all mandatory fields with valid data. | No error messages are visible. |
| 2 | Leave **"I agree to the T&C"** unchecked and Click on 'Pay Now' button. | Payment is blocked; the system triggers alert message "Terms and Conditions. You must agree to the terms and conditions to complete your purchase." |
| 3 | Check the box and proceed. | System allows navigation to the final payment confirmation. |

### TC_05: Dynamic Destination Insights (Climate Graph)
* **Technique:** Visual / Contextual UI Testing.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Book a specific planet (e.g., **"Madan"**). | Redirection to Checkout is successful. |
| 2 | Scroll to the **"Destination Insights"** section. | A yearly temperature graph for Madan is visible. |
| 3 | Verify graph legend. | Includes the text: *"Here is a yearly temp graph for your convenience ― pack accordingly"* (as per AC_3). |
