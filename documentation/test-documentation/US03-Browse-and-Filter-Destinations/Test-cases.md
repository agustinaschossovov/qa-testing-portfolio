# Test Case Mapping: Browse and Filter Destinations (US_03)

This mapping demonstrates the relationship between the business requirements (Acceptance Criteria), the testing techniques applied, and the specific test cases designed to ensure full coverage of the feature.

---

## 1. Test Scenarios Mapping

| Scenario ID | Test Scenario | Technique Applied | Acceptance Criteria Covered |
| :--- | :--- | :--- | :--- |
| **TC_01** | Combined Filtering (Planet + Color) | Decision Table (Rule 2) | AC_03 |
| **TC_02** | Single Filter (Planet only) | Decision Table (Rule 1) | AC_03 |
| **TC_03** | Single Filter (Color only) | Decision Table (Rule 3) | AC_03 |
| **TC_04** | Initial State / Default View (No Filters) | Decision Table (Rule 4) | AC_03 |
| **TC_05** | Negative Filtering (No Matching Results) | Negative Testing | AC_03 |
| **TC_06** | Price Slider Boundary Limits ($100 - $1800) | Boundary Value Analysis | AC_04 |
| **TC_07** | Dynamic Traveler & Date Summary update | Data Integrity / Calculation | AC_02 |
| **TC_08** | Destination Booking & State Transition | State Transition Testing | AC_05 |
| **TC_09** | Order Summary Integrity (Checkout) | Session / Data Integrity | AC_05, AC_06 |

---

## Test Design Technique: Decision Table (for TC_01, TC_02, TC_03, TC_04)

To ensure all logic combinations between "Launch" (Destination Planet) and "Planet Color" are covered, the following Decision Table was applied:

| Conditions (Inputs) | Rule 1 | Rule 2 | Rule 3 | Rule 4 |
| :--- | :---: | :---: | :---: | :---: |
| Launch (Planet) Selected? | **Y** | **Y** | N | N |
| Planet Color Selected? | N | **Y** | **Y** | N |
| **Action / Expected Result** | | | | |
| Show all results for that Planet | **X** | | | |
| Show specific Planet + Color match | | **X** | | |
| Show all Planets of that Color | | | **X** | |
| Show Default Grid (All) | | | | **X** |

---

## Critical Test Cases

### TC_01: Combined Filtering (Planet + Color)
* **Technique:** Decision Table (**Rule 2**)
* **Test Data:** `Launch: Shenji`, `Planet Color: Red`

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Open the "Launch" dropdown and select planet **"Shenji"**. | Grid updates to show destination Shenji. |
| 2 | Open the "Planet color" dropdown and select **"Red"**. | Grid filters to show only the **Red variant of Shenji**. |

### TC_02: Single Filter (Planet only)
* **Technique:** Decision Table (**Rule 1**)
* **Test Data:** `Launch: Madan`, `Planet Color: [None]`
* **Preconditions:** The dropdowns are in 'Planet Color' and in 'Launch'.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Select **"Madan"** planet from the Launch dropdown. | Grid displays the planet Madan, regardless of color. |
| 2 | Verify that the Color dropdown remains at default. | The planet Madan is visible in the results. |

### TC_03: Single Filter (Color only)
* **Technique:** Decision Table (**Rule 3**)
* **Test Data:** `Launch: [None]`, `Planet Color: Blue`

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Ensure the Launch dropdown is in its default state ('Launch'). | Full grid of destinations is displayed. |
| 2 | Select **"Blue"** from the Planet Color dropdown. | Grid filters to show **all planets** that are Blue. |

### TC_04: Initial State / Default View (No Filters)
* **Technique:** Decision Table (**Rule 4**)
* **Pre-conditions:** User navigates to the "Your Next Destination" section.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Observe the "Launch" (Planet) and "Planet Color" dropdowns. | Both dropdowns are in their default state, showing no active selection. |
| 2 | Check the destination grid without any user interaction. | The system displays the **full catalog** of destinations. |

### TC_05: Negative Filtering (No Matching Results)
* **Technique:** Negative Testing.
* **Test Data:** `Launch: Madan`, `Planet Color: Red`.
* **Preconditions:** The dropdowns are in 'Planet Color' and in 'Launch'.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Select planet **"Madan"** from the Launch dropdown. | Grid updates to show Madan destination. |
| 2 | Select the color **"Red"** from the Planet color dropdown. | The grid clears all cards since Madan has no Red variant. |
| 3 | Verify UI feedback. | The grid remains empty. |

### TC_06: Price Range Slider Boundary Limits
* **Technique:** Boundary Value Analysis (Min: $100, Max: $1800).

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Drag the price slider to the minimum (**$100**). | **Boundary "On":** Grid displays destinations starting from the $100 floor. |
| 2 | Drag the slider to a maximum of **$1800**. | **Boundary "On":** Destinations priced at exactly $1800 remain visible. |
| 3 | Verify a card with price **$1089.07**. | **Value "In":** The card remains visible as it is within the active range. |

### TC_07: Dynamic Summary Update (Dates & Travelers)
* **Test Data:** `Departing: Jan 3`, `Returning: Jan 16`, `Adults: 2`.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Select the specified Departure and Return dates. | Summary bar at the bottom displays: **"Jan 3 - 16"**. |
| 2 | Increase "Adults (18+)" to **2**. | Summary bar updates to: **"2 travelers"**. |
| 3 | Validate the full summary string. | Text displays: **"2 travelers, Jan 3 - 16"**. |

### TC_08: Destination Booking & State Transition
* **Technique:** State Transition Testing.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Click the **'BOOK'** button on a destination card. | Button text changes to **'BOOKED'** and a purple checkmark appears. |
| 2 | Observe system behavior. | User is automatically redirected to the **Checkout** page. |

### TC_09: Order Summary Integrity (Checkout)
* **Technique:** Data Integrity / Session Persistence.
* **Pre-conditions:** User has selected 2 travelers and dates Jan 3 - 16.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Navigate to the Checkout page after booking. | **Order Summary** panel correctly displays 2 travelers and Jan 3 - 16. |
| 2 | Verify the **Total** price calculation. | Total reflects [Unit Price x 2 travelers] (e.g., $2,178.14). |
