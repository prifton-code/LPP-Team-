# 📘 Bookstore App – QA Test Plan (Draft)

Project: Bookstore App – Web Application  
Version: Draft v1.0  
Date: 4th November 2025  
Prepared by: QA Team (Lena Ngarama, Prifton Mliwa, Peter Adebisi)  

---

## 1. Introduction & Objectives

-The purpose of this Test Plan is to define the strategy, scope, approach, resources, and schedule for testing the Bookstore App web application.
The test aims to ensure that the system meets both functional and non-functional requirements, delivers a consistent user experience, and aligns with the defined quality objectives.

### Objectives
1. Identify and document functional and non-functional defects.  
2. Validate user experience across devices and browsers.  
3. Ensure accessibility compliance (WCAG 2.1 AA).  
4. Assess security hygiene and data handling.  
5. Evaluate performance against defined budgets.  
6. Verify cross-platform responsiveness and consistency.  

---
## 2. Scope of Testing

### In Scope
- Functional verification of the following key features:  
  - User Authentication (Login, Sign-up, Logout)  
  - Book Catalog (Search, Filter, Sort, View Details)  
  - Shopping Cart (Add/Remove/Update Items)  
  - Checkout and Payment (mock/test mode)  
  - Order Management (View Orders, Order History)  
  - Admin Panel (CRUD operations for Books, Orders, Users)  
  - Notifications and Error Messages  

- Non-functional aspects including:  
  - Accessibility (keyboard navigation, ARIA roles, contrast ratios)  
  - Performance (page load, responsiveness, memory usage)  
  - Security hygiene (form validation, input sanitization, safe API calls)  
  - Browser & device compatibility  

### Out of Scope
- Integration with live payment gateways (real transactions)  
- Third-party analytics or marketing integrations  
- Backend infrastructure performance benchmarking  

---
## 3. Test Approach
Testing will follow a systematic, risk based approach combining manual and automated testing methods.

### Test Types & Activities
| Test Type | Description | Tools |
|------------|-------------|-------|
| Functional Testing| Validate all features meet requirements | Manual, Playwright/Selenium |
| Regression Testing| Ensure fixes and new features don’t break existing functionality | Playwright / Jest |
| Cross-Browser Testing | Verify layout and functionality on Chrome, Firefox, Edge | BrowserStack / Manual |
| Responsive Testing| Validate adaptability on mobile, tablet, and desktop | Chrome DevTools |
| Accessibility Testing | Evaluate compliance with WCAG 2.1 AA | axe DevTools, Lighthouse |
| Performance Testing| Measure load time and page responsiveness | Lighthouse, Chrome DevTools |
| Security Hygiene Testing| Check for common web vulnerabilities | OWASP ZAP, manual inspection |

---
## 4. Test Environment

| Environment | Description |
|--------------|--------------|
| Local| Developer & QA local machines using Node.js & npm environment |
| Staging| Shared testing server (URL TBD) |
| Browsers | Chrome (latest), Firefox (latest), Edge |
| Devices | Desktop (Windows, macOS), Mobile (Android, iPhone) |
| Test Data| Mock users, sample books, test payment details (sandbox keys) |

---
## 5. Test Items & Components

| Component | Description | Related Features |
|------------|--------------|------------------|
| Catalog | Displays list of available books | Search, Filter, Sort |
| Cart | Holds user-selected items | Add/Remove, Quantity Update |
| Checkout | Handles payment flow | Checkout Summary, Payment Validation |
| Orders | Displays previous purchases | Order History, Receipts |
| Admin| CRUD management | Add/Edit/Delete Books, Manage Users |
| Notifications | Alerts and confirmations | Toaster Messages, Errors |
| Accessibility  | Compliance testing | Keyboard Navigation, ARIA roles |
| Performance | Load and rendering speed | Lighthouse Metrics |

---
## 6. Entry & Exit Criteria
### Entry Criteria
- Application code is stable and builds successfully.  
- Required test data and environment are set up.  
- All dependencies installed successfully (npm install).  
- Jira/GitHub board set up with stories and tasks created.  

### Exit Criteria
- All planned test cases executed.  
- All Critical and Major defects fixed and verified.  
- Test coverage ≥ 90% of functional requirements.  
- Accessibility checks show no WCAG AA violations in main flows.  
- Performance goals met (Page load ≤ 2s on Chrome desktop).  
- Test summary report and evidence submitted.  

---
## 7. Test Deliverables

| Deliverable | Description |
|--------------|-------------|
| Test Plan | This document |
| Test Cases & Scenarios | Detailed test case list with IDs |
| Test Execution Logs| Pass/Fail status and evidence screenshots |
| Defect Reports | Logged bugs with steps to reproduce and severity |
| Test Summary Report | Overall findings, metrics, and final QA sign-off |
| Dashboard & Reports| Jira/GitHub dashboard screenshots and metrics |

---
## 8. Risks & Mitigation

| Risk | Impact | Mitigation |
|------|---------|------------|
| Unstable build or missing dependencies | High | Maintain version control; use package-lock.json |
| API keys or test credentials unavailable | High | Use mock/test data until keys are available |
| Tight deadlines (3-week window) | Medium | Prioritize critical user flows |
| Cross-browser inconsistencies | Medium | Use BrowserStack for parallel testing |
| Limited accessibility tools | Low | Use Chrome Lighthouse and axe-core extensions |

---

## 9. Schedule (3-Week Plan)

| Week | Activities | Deliverables |
|------|-------------|--------------|
| Week 1 (Nov 5) | Project kickoff, repo runs, board setup, draft test plan | Initial setup & Test Plan.md |
| Week 2 (Nov 11)| Test case design, test execution (functional & regression) | Test cases & evidence |
| Week 3 (Nov 18) | Retesting, report compilation, and submission | Final QA Report & Dashboard |

---

## 10. Traceability

All test cases and bugs will be traceable to the corresponding Functional Requirement (FR) or User Story ID using the following format:

- FR Codes: FR-CAT-001 (Catalog), FR-CART-002 (Cart), FR-CHK-003 (Checkout)  
- Bug IDs:BUG-001, BUG-002, etc.  
- Linking: Each bug linked to the related story or feature via Jira/GitHub Project.

---

## 11. Approval

| Name | Role | Signature | Date |
|------|------|------------|------|
| Lena Ngarama | QA Analyst |  |  |
| peter adebis | Test Executor |  |  |
| prifton mliwa | QA Lead |  |  |
| Supervisor | Project Reviewer |  |  |

---


