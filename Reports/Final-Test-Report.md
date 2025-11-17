# Software Test Report — Bookstore Application
*Version:* 1.0  
*Document ID:* TR-BOOKSTORE-FINAL  
*Date:* November 18, 2025  
*Prepared by:* QA Team — Bookstore Project

---

# 1. Executive Summary
This report presents the final results of testing the *Bookstore Web Application* from November 1–18, 2025.  
The QA effort focused on validating core shopping functionality, Paystack payment integration, and UI/UX stability.

*Key Findings*
- Core flows (browse → search → view → cart → pay) work correctly.
- Paystack integration stable after environment fix.
- Cart total miscalculation (high severity) remains the main blocker.
- API and search error messages require improvement.
- Overall pass rate: *84%* (27/32 test cases).

*Recommendation:*  
The QA team recommends *not releasing to full production* until the cart logic and error message handling are fixed. A *phased rollout (10%)* is acceptable after hotfix verification.

---

# 2. Test Objective
The primary objectives of this test cycle were:
1. Validate core bookstore functionality according to requirements.
2. Ensure Paystack payment integration works correctly in test mode.
3. Verify UI/UX quality, responsiveness, and error handling.
4. Identify defects early and provide a final readiness assessment.

---

# 3. Areas Covered

## 3.1 Functional Testing
- Homepage product listing  
- Book search (API & UI)  
- Product details view  
- Add/remove/update cart  
- Cart price calculation  
- Paystack payment flow  
- Navigation and routing  
- Basic authentication (if present)

## 3.2 Non-Functional Testing
- UI responsiveness  
- Mobile emulation testing  
- Error-handling usability  
- Basic performance (page load)  

---

# 4. Areas Not Covered
- Full backend load testing  
- Penetration testing  
- Admin dashboard (future feature)  
- Email/notification integration  
- Multi-browser extensive matrix

---

# 5. Testing Approach

## 5.1 Test Strategy
- *Risk-based testing* focusing on cart, search, payment.
- *Black-box testing* for UI and functionality.
- *Exploratory testing* for UX and failure states.

## 5.2 Test Process
1. *Week 1:* Planning, environment setup, test plan.  
2. *Week 2:* Drafting test cases, initial execution, early defect log.  
3. *Week 3:* Final execution, evidence collection, reporting.

---

# 6. Testing Tools
- Chrome DevTools  
- GitHub Project Boards  
- Postman  
- VS Code  
- Paystack Dashboard (Test Mode)

---

# 7. Test Execution Summary

| Metric | Result |
|---|---:|
| Total Test Cases | 32 |
| Executed | 32 |
| Passed | 27 |
| Failed | 5 |
| Blocked | 0 |
| Pass Rate | *84.4%* |

---

# 8. Detailed Test Cases

### 8.1 Homepage
| ID | Description | Result |
|---|---|---|
| TC-HOME-001 | Homepage loads with products | PASS |
| TC-HOME-002 | API loads product list | PASS |
| TC-HOME-003 | API failure shows user-friendly message | FAIL |

### 8.2 Search
| ID | Description | Result |
|---|---|---|
| TC-SRCH-001 | Search by title | PASS |
| TC-SRCH-002 | No-results state | PASS |
| TC-SRCH-003 | Search error handling | FAIL |

### 8.3 Cart
| ID | Description | Result |
|---|---|---|
| TC-CART-001 | Add item to cart | PASS |
| TC-CART-004 | Cart total correct when >3 items | FAIL |

### 8.4 Payment
| ID | Description | Result |
|---|---|---|
| TC-PAY-001 | Paystack key loads | PASS |
| TC-PAY-002 | Successful payment test | PASS |
| TC-PAY-003 | Currency shows as USD | PASS |

---

# 9. Defect Report

| Defect ID | Summary | Severity | Status |
|---|---|---:|---|
| BUG-001 | API error message unclear | Medium | Open |
| BUG-002 | Cart total incorrect when >3 items | High | Open |
| BUG-003 | Search error message unclear | Low | Open |
| BUG-004 | Navbar overlaps on mobile | Low | Fixed |
| BUG-005 | Cart link broken | Medium | Fixed |

*High Severity Defects:* 1 (Open)  
*Medium Severity Defects:* 1 open, 1 fixed  

---

# 10. Test Environment
- *Frontend:* React (Bookstore Project)  
- *Backend/API:* Mock + live API endpoints  
- *Payment:* Paystack Test Mode  
- *Browsers:* Chrome Desktop, Chrome Android  
- *OS:* Windows 10 / Android 10  

---

# 11. Overall Quality Assessment

## Strengths
- Payment flow is stable and user-friendly.
- Core shopping activities work smoothly.
- UI responsive for most screen sizes.

## Areas of Concern
- Cart total miscalculation affects billing integrity.
- Error messages are not user-friendly.
- Limited device/browser testing.

---

# 12. Risks

| Risk | Impact | Mitigation |
|---|---|---|
| Incorrect cart totals | High | Fix logic + regression tests |
| Unclear error messages | Medium | Standardize error-handling |
| Limited browser support | Medium | Expand compatibility testing |

---

# 13. Release Recommendation
*Recommendation:*  
❌ *NOT READY for full release.*  
✔ *OK for phased release (10%) AFTER hotfixes are applied and verified.*

---

# 14. Traceability Summary

| Requirement | Test Case(s) | Status |
|---|---|---|
| Product browsing | HOM-001, HOM-002 | Passed |
| Search functionality | SRCH-001 to SRCH-003 | Partial |
| Cart and checkout | CART-001 to CART-004 | Partial |
| Paystack integration | PAY-001 to PAY-003 | Passed |

---

# 15. Approvals
| Role | Name | Signature | Date |
|---|---|---|---|
| QA Lead | — | — | — |
| Developer Lead | — | — | — |
| Product Owner | — | — | — |

---

# End of Report