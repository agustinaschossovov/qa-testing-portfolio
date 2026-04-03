# User Story: Complete Space Travel Checkout (US_04)

## Description
**As an** end user,  
**I want to** automatically see the checkout section and destination details after clicking "BOOK",  
**so that** I can quickly complete my purchase while viewing helpful information like the local climate.

---

## Test Strategy & Applied Techniques (US_04)

### 1. State Transition Testing
* **Application:** Used for the "BOOK" button logic. 
* **Goal:** Verify the transition from the *Destination Gallery* (Selection State) to the *Checkout Section* (Transaction State). This ensures the UI scrolls correctly and the application state updates the "BOOKED" status.

### 2. Input Validation & Negative Testing
* **Application:** Applied to Name, Email, SSN, and Phone Number fields.
* **Goal:** To confirm that the system handles invalid data gracefully.
    * **Empty Fields:** Verification of "Required" constraints (AC_02).
    * **Regex/Masking:** Ensuring the SSN follows the `xxx-xx-xxxx` format and the Phone Number follows the AR (Argentinian) standard (AC_04).

### 3. Error Guessing (Manual)
* **Application:** Terms and Conditions checkbox.
* **Goal:** Testing the "Happy Path" vs. "Blocked Path". We verify that even with valid data in all fields, a single unselected checkbox (T&C) acts as a hard stop for the transaction (AC_03).

### 4. Visual/UI Testing
* **Application:** Temperature Guide (Madan Graph).
* **Goal:** Ensuring that the climate data is contextually relevant to the selected planet. It validates that the graph is not just a static image, but a dynamic component that provides value to the user's travel planning (AC_05).

### 5. Data Integrity & Persistence
* **Application:** Order Summary calculation.
* **Goal:** Validating that the data selected in the previous screen (US_03) persists without corruption.
    * **Formula:** `Total = (Destination Price) * (Number of Travelers)`.
