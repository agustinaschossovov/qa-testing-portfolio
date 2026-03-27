# Acceptance Criteria: User Log In (US_01)

This document details the functional and non-functional requirements that must be met for the User Login feature to be considered "Done".

## 📖 Requirement Overview
**As an** end user,  
**I need to** be able to log in using my username and password,  
**So that** I can securely access my account and personal travel bookings.

---

## ✅ Functional Criteria

### 1. Core Authentication
* **AC_01:** Verify that users can log in by entering a valid username and password.
* **AC_02:** Verify that clicking the "Log In" button authenticates the user successfully.
* **AC_03:** Verify that users are redirected to the main page (home/dashboard) after successful login.

### 2. Mandatory Field Validation
* **AC_04:** Verify that the **Username** field is required.
* **AC_05:** Verify that the **Password** field is required.
* **AC_06:** Verify that an error message appears when one or both fields are empty.
* **AC_07:** Verify that the form cannot be submitted with missing required fields.

### 3. Handling Invalid Credentials
* **AC_08:** Verify that the system validates the username and password against the database.
* **AC_09:** Verify that an error message appears when invalid credentials are entered.
* **AC_10:** **[Security]** Verify that the error message is generic and does not reveal which specific field is incorrect.

### 4. Cancel Button Behavior
* **AC_11:** Verify that the "Cancel" button is visible and enabled on the Login screen.
* **AC_12:** Verify that clicking the "Cancel" button cancels the login process.
* **AC_13:** Verify that users are redirected to the previous screen or the business-defined home page.

---

## 📱 Non-Functional Criteria (UI/UX)

### 5. Responsive Behavior (Mobile vs. Desktop)
* **AC_14:** Verify that the Login screen displays correctly on mobile devices.
* **AC_15:** Verify that all functional elements (inputs, buttons, and text) are visible and accessible across different screen sizes.
* **AC_16:** Verify that elements do not overlap or obstruct user interaction.
* **AC_17:** Verify that the login flow maintains logical order, even when the layout differs from the desktop version.
