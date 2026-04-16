# Bug Report: "PAY NOW" button is non-functional (Dead Link)

**ID:** BUG_004 

**User Story:** US_04 - Complete Space Travel Checkout

**Test Case Failed:** TC_04: Legal Consent (Terms & Conditions) Enforcement

**Priority:** **Critical** 

**Severity:** 🔴 **Blocker** 

**Status:** Open  

**Environment:** https://demo.testim.io/checkout

---

### Description
The **"PAY NOW"** button on the Checkout page does not trigger any action, redirection, or API call when clicked, even after all mandatory fields are correctly filled and the Terms & Conditions checkbox is checked. This prevents the user from completing the purchase process.

### Steps to Reproduce
1. Navigate to the **Checkout** page by booking a destination.
2. Fill in all mandatory personal information:
    * **Name:** Test User
    * **Email:** test@example.com
    * **SSN:** 123-45-6789
    * **Phone:** (Valid AR Format)
3. Check the **"I agree to the terms and conditions"** checkbox.
4. Verify the **"PAY NOW"** button is visually enabled.
5. Click the **"PAY NOW"** button.

### ❌ Actual Result
Nothing happens. No redirection to a success page, no loading spinner, and no console errors are visible to the user. The button acts as a static element.

### ✅ Expected Result
Upon clicking "PAY NOW" with valid data, the system should process the payment and redirect the user to a **Booking Confirmation** page or show a success message.

### Technical Environment
* **Browser:** Chrome / Firefox / Safari (Tested on multiple browsers)
* **Device:** Desktop & Mobile
* **Impact:** 100% of users are unable to complete checkout.

---
