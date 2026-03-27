# Test Documentation: User Log In (US_01)

## 🎯 1. User Story Description
**As an** end user,  
**I need to** be able to log in using my username and password,  
**So that** I can securely access my account and personal travel bookings.

---

## ✅ 2. Acceptance Criteria (AC)
* **AC_01:** Successful authentication with valid credentials.
* **AC_02:** Redirection to Home/Dashboard after successful login.
* **AC_03:** Generic error message for failed attempts (Security Best Practice).
* **AC_04:** Mandatory field validation (Username & Password).
* **AC_05:** "Cancel" button functionality.

---

## 🛠️ 3. Test Strategy & Techniques
For this feature, I applied the following design techniques to ensure quality:
* **Use Case Testing:** Validating the primary flow (Happy Path).
* **Equivalence Partitioning (EP):** Grouping invalid credentials to optimize test coverage.
* **State Transition:** Verifying the "Cancel" button's ability to return the system to its initial state.

---

## 🧪 4. Test Cases
| Case ID | Scenario | Technique | Expected Result |
| :--- | :--- | :--- | :--- |
| **TC_01** | Valid Log In | Use Case | Successful access to Home Page. |
| **TC_02** | Invalid Credentials | EP | Generic "Invalid credentials" error. |
| **TC_03** | Empty Mandatory Fields | Negative | Form cannot be submitted; validation alert. |
| **TC_04** | Cancel Login Process | State Transition | Redirection to the previous page. |

---

## 📸 5. Evidence & UI Verification
![Login View Showcase1](./login1.png)
![Login View Showcase2](./login2.png)

*Visual verification of the login interface (Desktop vs Mobile).*
