## 1. Test Scenarios Mapping

| Scenario ID | Test Scenario | Technique Applied | Acceptance Criteria Covered |
| :--- | :--- | :--- | :--- |
| **TC_08** | Destination Booking & State Transition | State Transition Testing | AC_05 |
| **TC_09** | Order Summary Integrity (Checkout) | Session / Data Integrity | AC_05, AC_06 |****

### TC_01: Destination Booking & State Transition
* **Technique:** State Transition Testing.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Click the **'BOOK'** button on a destination card. | Button text changes to **'BOOKED'** and a purple checkmark appears. |
| 2 | Observe system behavior. | User is automatically redirected to the **Checkout** page. |

### TC_02: Order Summary Integrity (Checkout)
* **Technique:** Data Integrity / Session Persistence.
* **Pre-conditions:** User has selected 2 travelers and dates Jan 3 - 16.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Navigate to the Checkout page after booking. | **Order Summary** panel correctly displays 2 travelers and Jan 3 - 16. |
| 2 | Verify the **Total** price calculation. | Total reflects [Unit Price x 2 travelers] (e.g., $2,178.14). |
