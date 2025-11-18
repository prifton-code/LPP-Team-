# Software Test Report — Bookstore Application
*Date:* November 18, 2025  
*Prepared by:* LPP Team — Bookstore Project

---

# 1. Executive Summary
This report presents the final results of testing the *Bookstore Web Application* from November 1–18, 2025.  
The QA effort focused on validating core shopping functionality, Paystack payment integration, and UI/UX stability.

## Key Findings
- Core flows (browse → search → view → cart → pay) work correctly.
- Paystack integration stable after environment fix.
- Cart total miscalculation (high severity) remains the main blocker.
- API and search error messages require improvement.
- Overall pass rate: *84%* (27/32 test cases).

*Recommendation:*  
The QA team recommends not releasing to full production until the cart logic and error message handling are fixed. A phased rollout (10%) is acceptable after hotfix verification.

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
- Basic authentication

## 3.2 Non-Functional Testing
- UI responsiveness  
- Mobile emulation testing  
- Error-handling usability  
- Basic performance (page load)  

---

# 4. Areas Not Covered
- Full backend load testing  
- Penetration testing  
- Admin dashboard  
- Email/notification integration  
- Multi-browser extensive matrix

---

# 5. Testing Approach

## 5.1 Test Strategy

- Risk-based testing focusing on payment, cart, and checkout flows
- Black-box functional testing for user journeys
- Accessibility compliance against WCAG 2.1 AA standards
- Cross-browser compatibility on major platforms
- Mobile responsiveness testing

---

## 5.2 Test Process
1. *Week 1:* Planning, environment setup, test plan.  
2. *Week 2:* Drafting test cases, initial execution, early defect log.  
3. *Week 3:* Final execution, evidence collection, reporting.

---

## 5.3  Test type Executed

| Test Type | Coverage | Tools Used |
|-----------|----------|------------|
| Functional Testing | 100% | Manual, Chrome DevTools |
| Payment Integration | 100% | Paystack Sandbox |
| Accessibility | 85% | axe DevTools, Screen Readers |
| Performance | 50% | Lighthouse, Chrome DevTools |
| Cross-browser | 75% | Chrome, Firefox |
| Mobile Responsive | 100% | Chrome Mobile Emulation |

---

# 6. Testing Tools
- Chrome DevTools  
- Jira Project Boards   
- VS Code  
- Paystack Dashboard (Test Mode)

---

# 7. Test Execution Summary

| Metric | Result |
|--------|--------|
| Total Test Cases | 32 |
| Executed | 32 |
| Passed | 27 |
| Failed | 5 |
| Blocked | 0 |
| Pass Rate | *84.4%* |

## 7.1 TEST Coverage by module

| Module Test Cases | Executed | Passed | Failed | Pass Rate |
|-------------------|----------|--------|--------|-----------|
| Catalog & Search | 13 |10 | 3 | 77% |
| Cart Management | 10 | 6 | 4 | 60% |
| Checkout & Payment | 7 | 5 | 2 | 71% |
| Order Management | 2 | 2 | 0 | 100% |
| Accessibility | 3 | 1 | 2 | 33% |
| Performance |2 | 1 | 1 | 50% |
| Total | 37 | 25 | 12 | 68% |

Note: Some test cases were consolidated from original 34 to 37 for comprehensive coverage


---

# 8. Sample Test Cases

### 8.1 Homepage
| ID | Description | Result |
|----|-------------|--------|
| TC-HOME-001 | Homepage loads with products | PASS |
| TC-HOME-002 | API loads product list | PASS |
| TC-HOME-003 | API failure shows user-friendly message | FAIL |

### 8.2 Search
| ID | Description | Result |
|----|-------------|--------|
| TC-SRCH-001 | Search by title | PASS |
| TC-SRCH-002 | No-results state | PASS |
| TC-SRCH-003 | Search error handling | FAIL |

### 8.3 Cart
| ID | Description | Result |
|----|-------------|--------|
| TC-CART-001 | Add item to cart | PASS |
| TC-CART-003 | Remove item from cart | PASS |
| TC-CART-004 |Cart perssistene across sessions | PASS |
| TC-CART-002 | Cart total correct when >3 items | FAIL |

### 8.4 Payment
| ID | Description | Result |
|----|-------------|--------|
| TC-CHK-001 | Paystack key loads | PASS |
| TC-CHK-002 | Successful payment test | PASS |
| TC-CHK-003 | Currency shows as USD | PASS |

---

# 9. Defect Report

## 9.1 Defect Distribution by Severity

| Severity | Count| Open | Fixed | Fix Rate |
|----------|------|------|-------|----------|
| Critical | 3 | 3 | 0 | 0% |
| Major | 7 | 5 | 2 | 29% |
| Minor | 4 | 4 | 0 | 0% |
| Cosmetic | 1 | 1 | 0 | 0% |
| Total | 15 | 13 | 2 | 13% |

## 9.2 Top 5 Critical/Major Defects

1. BUG-CART-001: Cart Quantity Price Calculation

· Status: OPEN | Severity: Critical
· Impact: Revenue calculation errors
· Description: Quantity updates visually but total price doesn't change
· Evidence: tests/evidence/FR-CART-002.png

2. BUG-CHK-003: Currency Mismatch

· Status: OPEN | Severity: Critical
· Impact: User confusion, potential legal issues
· Description: UI shows $ but payment gateway uses KES
· Evidence: tests/evidence/FR-CHK-003.png

3. BUG-CHK-008: Payment Button State Management

· Status: OPEN | Severity: Critical
· Impact: Blocks checkout process
· Description: Button remains disabled after form validation errors
· Evidence: tests/evidence/FR-CHK-008.png

4. BUG-SRCH-001: Search Results Persistence

· Status: OPEN | Severity: Major
· Impact: User experience confusion
· Description: Previous search results don't clear when input is emptied
· Evidence: tests/evidence/FR-CAT-003.jpg

5. BUG-A11Y-001: Missing Alt Text

· Status: OPEN | Severity: Major
· Impact: Accessibility compliance
· Description: Product images lack descriptive alt text
· Evidence: tests/evidence/FR-A11Y-002.png


---

# 10. Test Environment

| Component | Specification |
|-----------|---------------|
| Frontend | React 18, React Router 6, Tailwind CSS |
| Payment | Paystack Inline JS (Test Mode) |
| Storage | Browser localStorage with quota handling |
| Browsers | Chrome 118, Firefox 119 |
| Devices | Desktop (Windows/macOS), Mobile (Android) |
| Test Data | Mock books, test users, Paystack test card |

---

# 11. Overall Quality Assessment

## 11.1 Strengths by module

# payment Intergration

- Paystack test card processing working correctly
- Payment verification mock executing properly
- Order confirmation flow functioning

# Core Shopping Flow

- Product catalog displays correctly
- Basic search functionality operational
- Cart add/remove operations working
- Route navigation and redirects proper

# Admin Security

- Route guarding working as expected
- localStorage role-based access control functional

---

## 11.2 Areas of Concern


# Critical issues

1. Revenue Impact

- Cart total calculations incorrect
- Currency display mismatches
- Payment flow blocking issues


# Needs Improvements

1. Cart Management

- Quantity calculations inconsistent
- Price rounding issues present
- Persistence working but calculations flawed

2. Accessibility

- Missing alt text on product images
- Checkout modal missing ARIA attributes
- Keyboard navigation incomplete

3. User Experience

- Search persistence issues
- Form validation state problems
- Error handling not user-friendly

---

# 12. Risks Assessments

## 12.1 High Risk (Block Release)

| Risk |Impact | Probability | Mitigation |
|------|-------|-------------|------------|
| Revenue miscalculation | High | High | Fix cart calculation logic |
| Payment process blocking | High | Medium | Resolve button state issues |
| Legal compliance (currency) | High | Low | Align UI with payment currency |

## 12.2 Medium Risk (Should Fix)

| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|------------|
| Accessibility non-compliance | Medium | High | Implement WCAG fixes |
| User experience confusion | Medium | High | Improve search and form behavior |
| Cross-browser inconsistencies | Medium | Medium | Expand browser testing |

---

# 13. Release Recommendation
*Recommendation:*  
- *NOT READY for full release.*  
- *OK for phased release (10%) AFTER hotfixes are applied and verified.*

---

# 14. Traceability Summary

## 14.1 Requirements Coverage

| Functional Requirement | Test Cases | Status |
| FR-CART: Cart Management | TC-CART-001 to 010 | Partial |
| FR-CHK: Checkout Process | TC-CHK-006 to 009 | Partial |
| FR-CAT: Catalog & Search | TC-CAT-008 to 017 | Partial |
| FR-ORD: Order Management | TC-ORD-001 to 002 | Complete |
| FR-A11Y: Accessibility | TC-A11Y-001 to 003 | Poor | 
| FR-PERF: Performance | TC-PERF-001 to 002 | Partial |

---

# 15 RECOMMENDATIONS

## 15.1 Immediate Actions (Before Release)

1. Fix cart calculation logic - Address quantity update pricing issues
2. Resolve currency mismatch - Align UI display with payment gateway
3. Implement payment button state management - Prevent checkout blocking

## 15.2 Short-term Improvements (Next Sprint)

1. Accessibility compliance - Address WCAG 2.1 AA violations
2. Search functionality - Fix persistence and clearing behavior
3. Form validation - Improve user feedback and error handling

## 15.3 Long-term Strategy

1. Automated regression suite - Prevent calculation regressions
2. Performance monitoring - Implement Core Web Vitals tracking
3. Cross-browser testing - Expand browser compatibility matrix

---

# 16. Approvals
| Role | Name | Signature | Date |
|------|------|-----------|------|
| Project Lead | Prifton Mliwa| P.M | 17-11-2025 |
| Developer | Peter Adebisi | P.A | 17-11-2025 |
| Tester | Lena Wahu | L.W | 17-11-2025 |

---

# End of Report
![alt text](<PLP Logo.jpg>)