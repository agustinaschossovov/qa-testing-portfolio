# QA Testing Portfolio - By Agustina Schossovov

## Introduction
I am a **QA Analyst** with over **4+ years** of professional experience focused on ensuring the quality of web and mobile applications.

> [!IMPORTANT]
> This document is dynamic and will be updated over time to include additional testing types, demonstrating my adaptability to different project needs.

---

## Project: Space Advisor (Functional Testing)
**URL:** https://demo.testim.io/

**Devices:** Desktop / Mobile  

**Last Updated:** April 2026

### Overview
This project is a web application designed to provide **space travel booking services**. I used this site as a practice environment to apply formal manual functional testing techniques.

### Scope & Key Features
The testing focus is on core user flows to ensure a seamless booking experience:
* **User Authentication:** Log In process.
* **Search & Discovery:** Browse and Filter Space Travel Destinations.
* **Selection:** Destination selection logic.
* **Checkout:** Complete Space Travel Checkout flow.

---

## Repository Structure & Navigation

This project follows a modular documentation approach, organized by **User Story (US)** to ensure full traceability between requirements and test execution.

```text
/documentation
│
├── /bug-reports                # Detailed reports of identified defects
│   ├── BUG-001-Authentication-Bypass.md
│   ├── BUG-002-Returning-date-automatically-populated-by-Departing-date-selection.md
│   ├── BUG-003-Residual-Load-More-Button.md
│   ├── BUG-004-Pay-Now-is-Non-Functional.md
│   └── evidence              # Screenshots and media for bug reproduction
│
└── /test-documentation         # Core testing artifacts
    ├── /US01-user-login        # User Story Description, Acceptance Criteria & Test Cases for Authentication
    ├── /US02-Select-Destination...  # User Story Description, Acceptance Criteria & Test Cases for Booking Flow
    ├── /US03-Browse-and-Filter-Destinations  # User Story Description, Acceptance Criteria & Test Cases for Filtering
    ├── /US04-Complete-Space-Travel-Checkout...  # User Story Description, Acceptance Criteria & Test Cases for Checkout
    │
    ├── Test-Summary-Report.md  # Overall execution metrics & final assessment
    ├── requirement-analysis.md # Analysis of functional & non-functional requirements
    └── user-story-mapping.md   # High-level overview of the user journey

```

## QA Strategy & Applied Skills

For the **Space Advisor** project, I integrated my professional background with specific testing techniques to ensure high-quality delivery.

### Core Skills Applied:
* **Requirement Analysis & Documentation:** I performed a deep dive into the site's logic to create **User Stories** and **Acceptance Criteria** from scratch, applying a **Shift-Left Testing** approach.
* * **Execution & Defect Management:** I performed manual end-to-end execution, focusing on **Bug Reporting** and suggesting UX/UI improvements.
* **Traceability:** Maintained **Bidirectional Traceability** to ensure every requirement is covered by at least one test case.
* **Test Design:** I designed comprehensive **Test Scenarios** using two complementary approaches:
    * **Formal Test Case Structure:** Used for granular, step-by-step technical validation and maximum coverage.
    * **BDD (Behavior Driven Development):** Applied specifically to core user journeys using **Gherkin syntax** (Given/When/Then) to demonstrate readiness for collaboration and future automation.(Just used for TC01 and TC02 for test cases of US01)
* **Test Design Techniques:** I designed comprehensive **Test Scenarios** using formal Black-Box techniques:

## Testing Techniques Summary

The following table summarizes the strategic techniques applied across the 4 User Stories to ensure 100% logic coverage and high-quality standards.

| Technique | Purpose |
| :--- | :--- |
| **Equivalence Partitioning** | Optimizes the test suite by grouping valid and invalid input sets to reduce redundancy. |
| **Decision Table** | Ensures 100% coverage of all possible logic combinations between multiple filter variables. |
| **Boundary Value Analysis** | Detects "off-by-one" errors at the exact edges of numerical ranges and input limits. |
| **State Transition** | Validates the correct flow of the application from one status to another (e.g., Book -> Booked). |
| **Negative Testing** | Verifies system resilience and ensures that mandatory error messages trigger on invalid data. |
| **Data Integrity** | Confirms that user selection and session data persist without corruption across different pages. |
