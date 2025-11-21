# Software Test Report — Bookstore Application

**Date:** November 18, 2025
**Prepared by:** LPP Team — Bookstore Project

---

# 1. Executive Summary

This report presents the final results of testing the *Bookstore Web Application* from November 1–18, 2025. The QA effort focused on validating core shopping functionality, Paystack payment integration, and overall UI/UX stability.

## Key Findings

* Core flows (browse → search → view → cart → pay) work correctly.
* Paystack integration is stable after environment adjustments.
* Cart total miscalculation remains the most critical issue.
* Search and API error handling need improvement.
* Overall pass rate: **84%** (27/32 test cases).

**Recommendation:**
A full release should be delayed until critical issues, especially cart logic and currency inconsistencies, are fixed. A phased release (10% of users) is considered acceptable after successful hotfix verification.

---

# 2. Test Objective

The objectives of this testing cycle were:

1. Validate core bookstore functionality based on requirements.
2. Ensure Paystack payment flow works correctly in test mode.
3. Evaluate UI/UX quality, responsiveness, and usability.
4. Identify defects early and provide deployment readiness judgment.

---

# 3. Areas Covered

## 3.1 Functional Testing

* Homepage product listing
* Book search
* Product detail display
* Add/update/remove cart items
* Cart price calculations
* Paystack checkout flow
* Authentication and routing

## 3.2 Non-Functional Testing

* UI responsiveness
* Mobile device emulation
* Error-handling and usability
* Basic performance (page load)

---

# 4. Areas Not Covered

* Full backend performance/load testing
* Penetration testing
* Admin dashboard features
* Email/notification system
* Extensive multi-browser matrix

---

# 5. Testing Approach

## 5.1 Test Strategy

* Risk-based testing focused on checkout and cart functions.
* Black-box manual functional testing.
* Accessibility validation against WCAG 2.1 AA.
* Cross-browser checks on major platforms.
* Mobile display testing through emulation tools.

## 5.2 Test Process

1. **Week 1:** Planning, setup, test plan design
2. **Week 2:** Test case writing and early execution
3. **Week 3:** Final execution, evidence collection, reporting

## 5.3 Test Types Executed

| Test Type           | Coverage | Tools Used                   |
| ------------------- | -------- | ---------------------------- |
| Functional          | 100%     | Manual, Chrome DevTools      |
| Payment Integration | 100%     | Paystack Sandbox             |
| Accessibility       | 85%      | axe DevTools, Screen Readers |
| Performance         | 50%      | Lighthouse, Chrome DevTools  |
| Cross-browser       | 75%      | Chrome, Firefox              |
| Mobile Responsive   | 100%     | Chrome Mobile Emulation      |

---

# 6. Testing Tools

* Chrome DevTools
* Jira Project Board
* VS Code
* Paystack Dashboard (Test Mode)

---

# 7. Test Execution Summary

| Metric           | Result    |
| ---------------- | --------- |
| Total Test Cases | 32        |
| Executed         | 32        |
| Passed           | 27        |
| Failed           | 5         |
| Blocked          | 0         |
| **Pass Rate**    | **84.4%** |

## 7.1 Test Coverage by Module

| Module             | Executed | Passed | Failed | Pass Rate |
| ------------------ | -------- | ------ | ------ | --------- |
| Catalog & Search   | 13       | 10     | 3      | 77%       |
| Cart Management    | 10       | 6      | 4      | 60%       |
| Checkout & Payment | 7        | 5      | 2      | 71%       |
| Order Management   | 2        | 2      | 0      | 100%      |
| Accessibility      | 3        | 1      | 2      | 33%       |
| Performance        | 2        | 1      | 1      | 50%       |
| **Total**          | **37**   | **25** | **12** | **68%**   |

---

# 8. Sample Test Cases

## 8.1 Homepage

| ID          | Description                      | Result |
| ----------- | -------------------------------- | ------ |
| TC-HOME-001 | Homepage displays products       | PASS   |
| TC-HOME-002 | API fetches product list         | PASS   |
| TC-HOME-003 | API failure shows friendly error | FAIL   |

## 8.2 Search

| ID          | Description                     | Result |
| ----------- | ------------------------------- | ------ |
| TC-SRCH-001 | Search by title returns results | PASS   |
| TC-SRCH-002 | No-results message displays     | PASS   |
| TC-SRCH-003 | Search error message displays   | FAIL   |

## 8.3 Cart

| ID          | Description                       | Result |
| ----------- | --------------------------------- | ------ |
| TC-CART-001 | Item added to cart                | PASS   |
| TC-CART-003 | Item removed from cart            | PASS   |
| TC-CART-004 | Cart persists across sessions     | PASS   |
| TC-CART-002 | Cart total recalculated correctly | FAIL   |

## 8.4 Payment

| ID         | Description                  | Result |
| ---------- | ---------------------------- | ------ |
| TC-CHK-001 | Paystack key loads correctly | PASS   |
| TC-CHK-002 | Successful payment test      | PASS   |
| TC-CHK-003 | Currency displays as USD     | PASS   |

---

# 9. Defect Report

## 9.1 Defect Summary by Severity

| Severity  | Count  | Open   | Fixed | Fix Rate |
| --------- | ------ | ------ | ----- | -------- |
| Critical  | 3      | 3      | 0     | 0%       |
| Major     | 7      | 5      | 2     | 29%      |
| Minor     | 4      | 4      | 0     | 0%       |
| Cosmetic  | 1      | 1      | 0     | 0%       |
| **Total** | **15** | **13** | **2** | **13%**  |

---

## 9.2 Top 5 Critical & Major Defects

### 1. BUG-CART-001 – Cart Price Miscalculation

* **Status:** Open
* **Severity:** Critical
* **Impact:** Wrong revenue calculation
* **Issue:** Cart quantity updates but total price does not recalculate
* **Evidence:** `tests/evidence/FR-CART-002.png`

### 2. BUG-CHK-003 – Currency Mismatch

* **Status:** Open
* **Severity:** Critical
* **Impact:** User confusion and compliance issues
* **Issue:** UI displays USD while Paystack billing uses KES
* **Evidence:** `tests/evidence/FR-CHK-003.png`

### 3. BUG-CHK-008 – Payment Button State Issue

* **Status:** Open
* **Severity:** Critical
* **Impact:** Blocks successful checkout
* **Issue:** Button remains disabled after validation
* **Evidence:** `tests/evidence/FR-CHK-008.png`

### 4. BUG-SRCH-001 – Search Results Persist

* **Status:** Open
* **Severity:** Major
* **Impact:** Confusing user experience
* **Issue:** Search results remain visible even after clearing input
* **Evidence:** `tests/evidence/FR-CAT-003.jpg`

### 5. BUG-A11Y-001 – Missing Alt Text

* **Status:** Open
* **Severity:** Major
* **Impact:** Accessibility failure
* **Issue:** Product images lack descriptive `alt` tags
* **Evidence:** `tests/evidence/FR-A11Y-002.png`

---

# 10. Test Environment

| Component | Details                                           |
| --------- | ------------------------------------------------- |
| Frontend  | React 18, React Router 6, Tailwind CSS            |
| Payment   | Paystack Inline (Test Mode)                       |
| Storage   | Browser localStorage                              |
| Browsers  | Chrome 118, Firefox 119                           |
| Devices   | Windows / macOS / Android                         |
| Data      | Mock books, test users, Paystack test credentials |

---

# 11. Overall Quality Assessment

## 11.1 Strengths

### Payment Integration

* Paystack integration works correctly in test mode.
* Transaction verification functioning.

### Core Shopping Flow

* Catalog displays correctly
* Search returns correct results
* Add/remove cart actions work
* Navigational flow is clear

### Admin Security

* Role checking and protected routes functioning

---

## 11.2 Areas of Concern

### High Impact (Critical)

* Incorrect cart billing calculation
* Currency mismatch in payment flow
* Checkout button state issues

### Needs Improvement

* Accessibility: alt tags, ARIA roles, keyboard navigation
* Search clearing and state management issues
* Error messaging could be more user-friendly

---

# 12. Risk Assessment

## 12.1 High Risk (Blocks Release)

| Risk                   | Impact | Probability | Mitigation                    |
| ---------------------- | ------ | ----------- | ----------------------------- |
| Billing miscalculation | High   | High        | Fix cart logic                |
| Payment blocking       | High   | Medium      | Repair button state logic     |
| Currency mismatch      | High   | Low         | Align UI and Paystack display |

## 12.2 Medium Risk (Recommended Fix)

| Risk                 | Impact | Probability | Mitigation                    |
| -------------------- | ------ | ----------- | ----------------------------- |
| Accessibility issues | Medium | High        | Implement WCAG improvements   |
| UX confusion         | Medium | High        | Improve search and form logic |
| Browser differences  | Medium | Medium      | Expand browser testing        |

---

# 13. Release Recommendation

**Recommendation:**

* **NOT READY for full public release.**
* **Safe for controlled 10% rollout after fixes and retesting.**

---

# 14. Requirements Traceability

| Requirement               | Test References    | Status   |
| ------------------------- | ------------------ | -------- |
| FR-CART (Cart)            | TC-CART-001 to 010 | Partial  |
| FR-CHK (Checkout)         | TC-CHK-006 to 009  | Partial  |
| FR-CAT (Catalog & Search) | TC-CAT-008 to 017  | Partial  |
| FR-ORD (Orders)           | TC-ORD-001 to 002  | Complete |
| FR-A11Y (Accessibility)   | TC-A11Y-001 to 003 | Poor     |
| FR-PERF (Performance)     | TC-PERF-001 to 002 | Partial  |

---

# 15. Recommendations

## 15.1 Immediate Before Release

1. Fix cart pricing logic
2. Resolve payment currency mismatch
3. Correct payment button state handling

## 15.2 Next Sprint Improvements

1. Accessibility fixes
2. Search behavior improvements
3. Better form validation and user messaging

## 15.3 Long Term Strategy

1. Automated regression testing
2. Performance monitoring
3. Wider browser compatibility coverage

---

# 16. Approvals

| Role         | Name          | Signature | Date       |
| ------------ | ------------- | --------- | ---------- |
| Project Lead | Prifton Mliwa | P.M       | 17-11-2025 |
| Developer    | Peter Adebisi | P.A       | 17-11-2025 |
| Tester       | Lena Wahu     | L.W       | 17-11-2025 |

---

# 17. Appendix

## 17.1 Complete Test Case Inventory

| Test Case ID | Module | Description | Priority | Status | Defect ID | Evidence File |
|--------------|--------|-------------|----------|--------|-----------|---------------|
| TC-HOME-001 | Homepage | Homepage loads with products | High | PASS | - | /tests/evidence/FR-HOME-001.png |
| TC-HOME-002 | Homepage | API loads product list | High | PASS | - | /tests/evidence/FR-HOME-002.png |
| TC-HOME-003 | Homepage | API failure shows user-friendly message | Medium | FAIL | BUG-API-001 | /tests/evidence/FR-HOME-003.png |
| TC-SRCH-001 | Search | Search by title | High | PASS | - | /tests/evidence/FR-SRCH-001.png |
| TC-SRCH-002 | Search | No-results state | Medium | PASS | - | /tests/evidence/FR-SRCH-002.png |
| TC-SRCH-003 | Search | Search error handling | Medium | FAIL | BUG-SRCH-001 | /tests/evidence/FR-SRCH-003.png |
| TC-CART-001 | Cart | Add item to cart | High | PASS | - | /tests/evidence/FR-CART-001.png |
| TC-CART-002 | Cart | Cart total correct when >3 items | High | FAIL | BUG-CART-001 | /tests/evidence/FR-CART-002.png |
| TC-CART-003 | Cart | Remove item from cart | High | PASS | - | /tests/evidence/FR-CART-003.png |
| TC-CART-004 | Cart | Cart persistence across sessions | Medium | PASS | - | /tests/evidence/FR-CART-004.png |
| TC-CHK-001 | Payment | Paystack key loads | High | PASS | - | /tests/evidence/FR-CHK-001.png |
| TC-CHK-002 | Payment | Successful payment test | High | PASS | - | /tests/evidence/FR-CHK-002.png |
| TC-CHK-003 | Payment | Currency shows as USD | High | PASS | - | /tests/evidence/FR-CHK-003.png |
| TC-A11Y-001 | Accessibility | Screen reader compatibility | Medium | FAIL | BUG-A11Y-001 | /tests/evidence/FR-A11Y-001.png |
| TC-PERF-001 | Performance | Page load under 3 seconds | Medium | PASS | - | /tests/evidence/FR-PERF-001.png |

> *Note:* All evidence files are stored in the `/tests/evidence` folder.

---

## 17.2 Test Data References

### 17.2.1 Test User Accounts
| User Type     | Email                  | Password  | Role          | Notes                     |
| ------------- | -------------------- | -------- | ------------ | ------------------------- |
| Standard User | test.user@bookstore.com | Test123! | Customer     | Functional testing user   |
| Admin User    | admin@bookstore.com    | Admin123!| Administrator | Admin functionalities     |

### 17.2.2 Payment Test Cards (Paystack Test Mode)
| Card Type | Card Number           | CVV | Expiry  | Expected Result |
| ---------- | ------------------- | --- | ------- | --------------- |
| Approved   | 4084 0840 8408 4081 | 408 | 01/30  | Payment Pass |
| Declined   | 4084 0840 8408 4082 | 408 | 01/30  | Payment Fail    |

---

## 17.3 Screenshots & Evidence Folder Structure


> *All referenced images provide visual proof of test execution, including UI states, logs, and network/output details.*

---

## 17.4 Sample Test Case Template Used

| Field           | Description                           |
| --------------- | ------------------------------------- |
| Test Case ID    | Unique identifier (e.g., TC-CART-001) |
| Module          | Functional module being validated     |
| Pre-conditions  | Requirements before execution         |
| Steps           | Actions performed                     |
| Expected Result | What should happen                    |
| Actual Result   | Outcome observed                      |
| Result          | PASS / FAIL                           |
| Evidence        | Screenshot or log reference           |

---

## 17.5 Sample Bug Report Template Used

| Field                 | Description                       |
| --------------------- | --------------------------------- |
| Bug ID                | Unique ID, e.g., BUG-CART-001    |
| Module                | Area affected                     |
| Severity              | Critical / Major / Minor          |
| Description           | Summary of issue                  |
| Steps to Reproduce    | How to trigger the defect         |
| Expected Result       | Intended behavior                 |
| Actual Result         | What happened instead             |
| Screenshot / Evidence | File reference                    |
| Assigned To           | Developer responsible             |
| Status                | Open / Fixed / Retesting          |

---

## 17.6 Tools Version Table

| Tool            | Version         |
| --------------- | --------------- |
| Chrome Browser  | 118             |
| Firefox Browser | 119             |
| React           | 18              |
| Tailwind CSS    | 3.x             |
| Paystack JS SDK | Test Mode Build |
| Lighthouse      | V10             |
| VS Code         | Latest Stable   |
| Jira            | Latest Stable   |

---

## 17.7 Test Team Members

| Name          | Role         |
| ------------- | ------------ |
| Prifton Mliwa | Project Lead |
| Peter Adebisi | Developer    |
| Lena Wahu     | QA Tester    |

---

## 17.8 Additional Notes

- The appendix contains all evidence and references to allow **audit and verification** of test execution.  
- Full environment and tool versions included to ensure **reproducibility**.  
- Test case templates and bug report templates standardize documentation for the team.  

---
![PLP Academy Logo](<img width="3000" height="1688" alt="plp logo" src="https://github.com/user-attachments/assets/2678a230-7bae-40fa-b28e-164d09001bb8" />)
# End of Report
