# Bug Report: Authentication Bypass on Login Screen

**Bug ID:** BUG-001  

**Status:** Open  

**Severity:** Critical 🔴  

**Priority:** High  

**User Story:** User Login 

**Environment:** `https://demo.testim.io/`  

**Test Case Failed:** US01-user-login --> TC_03: Invalid Credentials (Negative Testing) 

---

## Description
The login functionality fails to validate user credentials. The system grants access to the "Main Page" regardless of the input provided in the Username and Password fields, including invalid data and extreme character lengths (1000+).

---

## Steps to Reproduce
1. Navigate to `https://demo.testim.io/`.
2. Click on the "Log In" button in the header.
3. Enter invalid credentials (e.g., Username: `wrong_user`, Password: `invalid_password`).
4. Click the "Log In" button.
5. Click on the "Log In" button in the header.
6. Enter valid username: user1. Paste a 1000+ character string in the Password field.
7. Click the "Log In" button.

## ❌ Actual Result
The system redirects the user to the Main Page and provides full access to the application features.

## ✅ Expected Result
The system should validate the credentials against the database, deny access, and display a generic "Invalid credentials" error message.

## Technical Note
This is a critical security vulnerability (**Authentication Bypass**). It suggests a lack of server-side validation or a hardcoded redirect logic in the front-end that bypasses the authentication service.
