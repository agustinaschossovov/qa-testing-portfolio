# Acceptance Criteria: Select Space Travel Destination (US_02)

## 📖 Requirement Overview

**As an** end user, 

**I want to** select travel details such as departure date, return date, and number of passengers from the hero banner,

**So that** I can proceed to the next step and view available space travel destinations.

## 1. Display of Hero Banner Input Fields
* **AC_01:** The hero banner must display the following fields: **Departing**, **Returning**, **Adults (18+)**, and **Children (0-7)**.
* **AC_02:** All input fields must be visible and enabled upon page load.
* **AC_03:** "Departing" and "Returning" fields must trigger a **Date Picker** when clicked.
* **AC_04:** "Adults (18+)" and "Children (0-7)" must display a dropdown list with values: **1, 2, 3, 4**.
* **AC_05:** **Default Values:**
    * Dates: Current date (Today).
    * Adults: "Adults (18+)".
    * Children: "Children (0-7)".

## 2. Date Selection Validation
* **AC_06:** Users must be able to select a valid Departure date.
* **AC_07:** The Return date must be equal to or later than the Departure date.
* **AC_08:** The system must prevent selecting a Return date earlier than the Departure date.

## 3. Passenger Quantity Selection
* **AC_09:** If "Adults" is left at default and "Select Destination" is clicked, the system must automatically set it to **1** and move the label above the input.
* **AC_10:** The 'Your Next Destination' grid must reflect the total count of travelers correctly (e.g., 4 Adults + 1 Child = **5 travelers**).

## 4. Button Behavior
* **AC_11:** The "Select Destination" button must be visible and enabled when travel details are complete.
* **AC_12:** Clicking the button must navigate the user to the 'Your Next Destination' results grid.
* **AC_13:** Selected travel details must be preserved and used to filter the displayed destinations.

## 5. Responsive Behavior
* **AC_14:** All elements must render correctly on both desktop and mobile devices without overlapping.
