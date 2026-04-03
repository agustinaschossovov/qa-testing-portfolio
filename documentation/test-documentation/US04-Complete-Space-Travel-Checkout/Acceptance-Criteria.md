### 5. Booking & Cards Behavior
* **State Transition:** Verify that clicking **'BOOK'** changes the button state to **'BOOKED'** and adds a check icon in the upper right corner of the card.

![state-transition](./us3-ac5.1.png)
 
* **Session Persistence:** Verify that clicking 'BOOK' successfully captures the item's unique identifier and redirects to the **Checkout page** with the item in the session.
* **UI Resilience:** * Verify layout stability on different screen sizes.
    * Verify that clicking the card body (image/text) does nothing (read-only).
    * Verify that long titles or broken images do not break the card's design.
 
### 6. Checkout Process & Forms
* **Form Fields:** Verify that the Checkout page displays fields for: *Name, Email Address, Social Security Number, and Phone Number.*
* **Order Summary:** Verify that the "Order Summary" correctly displays:
    * Selected Dates (e.g., Jan 3 - 16).
    * Number of travelers.
    * Unit price and Total price (calculated correctly).
* **Promo Code:** Verify that the 'I have a promo code' field is visible and the 'APPLY' button is functional.
* **Health Insurance Upload:** Verify that the drag-and-drop area for "Health insurance" is visible and accepts file uploads.

### 7. Destination Insights (Contextual Info)
* **Temperature Graph:** Verify that when a destination is booked (e.g., Shenji), a yearly temperature graph/chart is displayed to help the user pack accordingly.
