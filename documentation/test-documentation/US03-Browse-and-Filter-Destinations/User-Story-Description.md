# Test Documentation: Browse and Filter Destinations (US_03)

## 1. User Story Description

**As an** end user,
**I want to** browse and filter available space travel destinations,
**So that** I can compare options and choose the destination that best fits my preferences and budget.

## 2. Test Strategy & Techniques

For this feature, I applied the following design techniques to ensure a robust filtering system and correct data persistence:

* **Combinatorial Testing:** Validating the interaction between the **Launch** site and **Planet Color** dropdowns to ensure the grid updates accurately when multiple filters are active.
* **Boundary Value Analysis (BVA):** Testing the **Price Range Slider** at its minimum ($100) and maximum ($1800) limits to verify that the results grid strictly respects the defined budget boundaries.
* **State Transition Testing:** Verifying the UI changes when clicking the **"BOOK"** button (changing to **"BOOKED"** with a check icon) and the subsequent transition to the Checkout page.
* **Data Integrity Testing:** Confirming that selecting dates and travelers in the hero banner correctly reflects in the **"Traveler and date summary information"** (e.g., "Jan 3 - 9") and carries over to the Checkout Order Summary.
* **UI/UX Robustness:** Testing the grid's resilience against long destination titles (e.g., "Sant Cugat Del Valles") and ensuring functional integrity even if a destination image fails to load.

---
