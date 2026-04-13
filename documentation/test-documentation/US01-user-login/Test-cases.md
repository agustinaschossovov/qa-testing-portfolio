# Test Case Specification: User Log In (US_01)

This document contains the prioritized test cases for the Login functionality, demonstrating the application of different testing techniques.

## 1. Test Scenarios Mapping (US_01: User Log In)

| Scenario ID | Test Scenario | Technique Applied | Acceptance Criteria Covered |
| :--- | :--- | :--- | :--- |
| **TC_01** | Successful Log In (Happy Path) | **Use Case Testing** | AC_01, AC_02 |
| **TC_02** | Mandatory Field Validation (Empty inputs) | **Equivalence Partitioning (Neg.)** | AC_03, AC_04 |
| **TC_03** | Invalid Credentials & Boundary Limits | **EP & Error Guessing** | AC_03, AC_05 |
| **TC_04** | Password Masking (Visual Security) | **Security / UI Validation** | AC_06 |
| **TC_05** | Cancel Button Behavior | **State Transition Testing** | AC_07 |

---

## Critical Test Cases

### TC_01:

 Scenario: Successful login with valid credentials (Happy Path)
 
    Given the user is on "https://demo.testim.io/"
    When the user clicks on "Log In" in the header
    Then the login view should be displayed

    When the user enters username "user1"
    And the user enters password "user1234"
    Then the fields should accept the input

    When the user clicks on "Log In" button
    Then the user should be redirected to the main page
    And the header should display "Hello, John"
    And the "Log In" option should not be visible
---

### TC_02: 

* **Technique:** Equivalence Partitioning (Negative).

Scenario: Login fails when mandatory fields are empty
   
    Given the user is on the login page
    When the user enters username "<username>"
    And the user enters password "<password>"
    And the user clicks on "Log In" button
    Then the login should be prevented
    And an error message "<error_message>" should be displayed

    Examples:
      | username | password  | error_message                        |
      | user1    |           | Password is a required field.        |
      |          | user1234  | Name is a required field.            |

---

### TC_03: Invalid Credentials (Negative Testing)
* **Technique:** Equivalence Partitioning & Error Guessing.
* **Test Data:** `User: user1` | `Pass: invalid_pass_123` / `Pass: [1000+ characters]`

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Enter a valid username but an incorrect password. | Characters are masked for security. |
| 2 | Enter a valid username and a 1000+ character string as password. | System should ideally truncate input or show a validation error. |
| 3 | Click "Log In". | **Login fails; a generic "Invalid credentials" error message is displayed.** |

---

### TC_04: Password Masking (Visual Security)
* **Technique:** Security Testing / UI Validation.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | Navigate to the Login screen. | - |
| 2 | Enter any string in the Password field. | **Characters are masked (bullets/asterisks) to ensure privacy and prevent shoulder surfing.** |

---

### TC_05: Cancel Button Behavior
* **Technique:** State Transition Testing.

| Step | Action | Expected Result |
| :--- | :--- | :--- |
| 1 | On the Login screen, click the "Cancel" button. | Login process is interrupted. |
| 2 | Observe the redirection. | **User is redirected back to the previous screen or Home Page.** |
