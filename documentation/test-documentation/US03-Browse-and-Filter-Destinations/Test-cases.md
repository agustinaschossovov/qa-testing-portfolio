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

* **Technique:** Boundary Value Analysis (BVA).
* **Objective:** Verify the system's precision at the exact edge cases of the price range ($100 - $1800).
* **Test Data:** Boundaries ($100, $1800), off-points ($99, $1801) and an inside range ($1089).

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Drag the price slider to the **Lower Boundary ($100)**. | Destinations priced at exactly $100 remain visible (Neither of the planets costs $100 so the grid remains empty). |
| 2 | Attempt to find a destination priced at **$99**. | The input updates to $100 when trying to write $99 because the system does not accept entering numbers below $100. |
| 3 | Drag the slider to the **Upper Boundary ($1800)**. | Destinations priced between $100 and $1800 remain visible. |
| 4 | Verify a destination priced at **$1801**. | The input updates to $1800 when trying to write $1801 because the system does not accept entering numbers above $1800. |
| 5 | Filter for a value **Inside** the range (e.g., **$1089**). | The destinations that costs between $100 and $1089 remains visible. |

### TC_07: Dynamic Summary Update (Dates & Travelers)
* **Test Data:** `Departing: Current date`, `Returning: Current date + 4 days`, `Adults(+18): 2`, **`Children(0-7): 2`**.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Select the specified Departure and Return dates. | Summary bar at the bottom displays: **"Current date - Current date + 4 days"**. |
| 2 | Increase "Adults (18+)" to **2** and "Children(0-7)" to **2**. | Summary bar updates to: **"4 travelers"**. |
| 3 | Validate the full summary string. | Text displays: **"4 travelers, Current date - Current date + 4 days"**. |

![Example](./us3-ac2.1.png)

