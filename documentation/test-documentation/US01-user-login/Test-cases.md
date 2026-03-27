# Test Case Specification: User Log In (US_01)

This document contains the prioritized test cases for the Login functionality, demonstrating the application of different testing techniques.

## 🧪 Top 5 Critical Test Cases

### TC_01: Valid Log In (Happy Path)
* **Technique:** Use Case Testing.
* **Priority:** High
* **Pre-conditions:** Browser open at `https://demo.testim.io/`.
* **Test Data:** `User: user1` | `Pass: user1234`

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Enter the URL and click "Log In" from the header. | Login view is displayed correctly. |
| 2 | Enter valid username and password. | Fields accept the input. |
| 3 | Click "Log In" button. | **Page redirects to the Main Page.** |
| 4 | Verify the header content. | **"Hello, John" appears in the header instead of "Log In".** |

---

### TC_02: Mandatory Field Validation (Empty Password)
* **Technique:** Equivalence Partitioning (Negative).
* **Priority:** Medium

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Enter a valid username but leave the Password field empty. | Input accepted in username. |
| 2 | Click "Log In". | **System prevents login and an error message appears "Password is a required field."** |

---

### TC_03: Invalid Credentials (Negative Testing)
* **Technique:** Equivalence Partitioning & Error Guessing.
* **Priority:** High
* **Test Data:** `User: user1` | `Pass: invalid_pass_123` / `Pass: [1000+ characters]`

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Enter a valid username but an incorrect password. | Characters are masked for security. |
| 2 | Enter a valid username and a 1000+ character string as password. | System should ideally truncate input or show a validation error. |
| 3 | Click "Log In". | **Login fails; a generic "Invalid credentials" error message is displayed.** |

---

### TC_04: Generic Error Message (Security Best Practice)
* **Technique:** Security Testing.
* **Priority:** Medium

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Attempt to log in with an unregistered username. | - |
| 2 | Click "Log In". | **The error message is generic and does not reveal which field is incorrect (Security).** |

---

### TC_05: Cancel Button Behavior
* **Technique:** State Transition Testing.
* **Priority:** Low

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | On the Login screen, click the "Cancel" button. | Login process is interrupted. |
| 2 | Observe the redirection. | **User is redirected back to the previous screen or Home Page.** |
