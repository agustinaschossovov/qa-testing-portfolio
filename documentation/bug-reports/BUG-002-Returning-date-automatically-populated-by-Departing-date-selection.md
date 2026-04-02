# Bug Report: Returning date automatically populated by Departing date selection

**Status:** 🔴 Open  
**Severity:** High (Business Logic Violation)  
**Priority:** High  
**Environment:** https://demo.testim.io/   

---

### Description
In the **Space Advisor** search feature, selecting a **Departing date** triggers an unintended automatic update to the **Returning date** field. This behavior forces a date into the return field before the user has made a choice.

**Linked Test Case:** `US02-Select-Destination` --> `TC-01 Valid Travel Selection (Happy Path)`

---

### Steps to Reproduce
1. Navigate to the booking page: [https://demo.testim.io/](https://demo.testim.io/)
2. Click on the **"Departing"** date picker.
3. Select any valid date from the calendar.
4. Observe the **"Returning"** date input field.

---

### ❌ Actual Result
The **"Returning"** date field is automatically populated with a value as soon as the **"Departing"** date is selected.

### ✅ Expected Result
The **"Returning"** date field should remain **empty (null)** until the user explicitly selects a return date. The departure selection should not influence the state of the return field.

---
