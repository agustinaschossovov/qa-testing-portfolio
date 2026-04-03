## 1. Test Scenarios Mapping

| Scenario ID | Test Scenario | Technique Applied | Acceptance Criteria Covered |
| :--- | :--- | :--- | :--- |
| **TC_01** | Destination Booking & State Transition | State Transition Testing | AC_01 |
| **TC_02** | Order Summary Integrity (Checkout) | Session / Data Integrity | AC_01, AC_02 |****

### TC_01: Destination Booking & State Transition
* **Technique:** State Transition Testing.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Click the **'BOOK'** button on a destination card. | Button text changes to **'BOOKED'** and a purple checkmark appears. |
| 2 | Observe system behavior. | User is automatically redirected to the **Checkout** page. |

### TC_02: Order Summary Integrity (Checkout)
* **Technique:** Data Integrity / Session Persistence.
* **Pre-conditions:** User has selected 2 travelers and dates Any date - Any date.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Navigate to the Checkout page after booking. | **Order Summary** panel correctly displays 2 travelers and Any date - Any date. |
| 2 | Verify the **Total** price calculation. | Total reflects [Unit Price x 2 travelers]. |
