# Test Case Specification: Select Space Travel Destination (US_02)

This document details the test scenarios and cases for the travel selection banner, applying advanced testing techniques to ensure data integrity and a smooth user experience.

## 1. Test Scenarios Mapping
| Scenario ID | Test Scenario | Technique Applied | AC Covered |
| :--- | :--- | :--- | :--- |
| **1** | Successful destination selection (Happy Path) | Use Case Testing | AC_01 to AC_05, AC_11, AC_12 |
| **2** | Invalid date range (Return before Departure) | Equivalence Partitioning (Invalid) | AC_07, AC_08 |
| **3** | Passenger quantity boundary limits (1 & 4) | Boundary Value Analysis | AC_04, AC_09 |
| **4** | Automatic passenger correction (Default state) | Negative Testing / Business Logic | AC_09 |
| **5** | Dynamic data reflection in Results Grid | Data Integrity / Calculation | AC_10, AC_13 |

---

## 2. Test Cases

### TC_01: Valid Travel Selection (Happy Path)
* **Priority:** High
* **Test Data:** `Departing: Today`, `Returning: Today + 5`, `Adults: 2`, `Children: 1`

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Navigate to the main page. | Hero banner is visible with default dates. |
| 2 | Select a valid Departure and Return date. | Date picker closes and dates are displayed. |
| 3 | Select "2" in Adults and "1" in Children. | Dropdowns reflect the selected numbers. |
| 4 | Click "Select Destination" button. | **User is navigated to the 'Your Next Destination' grid.** |

---

### TC_02: Invalid Date Selection (Return < Departure)
* **Technique:** Equivalence Partitioning.
* **Priority:** Medium
* **Pre-conditions:** User has selected a Departure date (e.g., Jan 15).

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Open the "Returning" date picker. | Calendar is displayed. |
| 2 | Attempt to select a date prior to Jan 15. | **System prevents selection (date is disabled) or displays a validation error.** |

---

### TC_03: Boundary Value Analysis - Passenger Dropdowns
* **Technique:** Boundary Value Analysis (Min: 1, Max: 4).
* **Priority:** Medium

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Click on "Adults (18+)" dropdown. | List displays values from 1 to 4. |
| 2 | Select the minimum value (1). | Value is accepted. |
| 3 | Select the maximum value (4). | Value is accepted. |
| 4 | Verify that values < 1 or > 4 are not available. | **Input is restricted to the defined boundary (1-4).** |

---

### TC_04: Default Passenger Logic (Business Rule)
* **Technique:** Negative Testing.
* **Priority:** Low

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Leave "Adults (18+)" in its default state. | Label shows "Adults (18+)". |
| 2 | Click "Select Destination". | **Field is automatically set to "1" and the label moves above the input.** |

---

### TC_05: Calculation Accuracy in Results Grid
* **Technique:** Data Integrity.
* **Test Data:** `Adults: 4`, `Children: 1`

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Select 4 Adults and 1 Child. | Input fields are updated. |
| 2 | Click "Select Destination". | - |
| 3 | Verify the summary text in the results grid. | **Text displays "5 travelers" along with the correct date range.** |
