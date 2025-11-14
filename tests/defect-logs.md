# 🐞 Bookstore App — Defect Log (Week 2)
Team: LPP Team  
Project: Bookstore Web Application  
Phase: Week 2 — Test Design & Early Execution  
Date: November 13, 2025  
Prepared by: LPP Team  

---

## 🧩 Overview
This defect log documents bugs and usability issues detected during Week 2 testing of the Bookstore App.  
Testing covered routing, navigation, checkout workflow, and accessibility of major components (App.js, Navbar.js, and CheckoutPage.js).

---

| ID | Date | Component | Summary | Steps to Reproduce | Expected Result | Actual Result | Evidence | Severity | Status | Reporter |
|----|------|-----------|----------|--------------------|-----------------|----------------|-----------|-----------|--------|-----------|
| BUG001 | 13/11/2025 | CheckoutPage | 'Pay Now' button allows multiple clicks | 1. Proceed to checkout 2. Click 'Pay Now' repeatedly | Only one payment request should trigger | Multiple payment attempts processed when clicked quickly | [Link to screen recording] | Critical | Open | Lena |
| BUG002 | 13/11/2025 | CheckoutPage | Missing input validation for postal code format | 1. Enter letters in postal code 2. Click 'Next'| Should display validation error | Form proceeds without validating postal code | [Link to screenshot] | Major | Open | Lena |
| BUG003 | 13/11/2025 | CheckoutPage | Invalid email accepted | 1. Enter abc@ as email 2. Click 'Next' | Should show "Enter valid email" error | Form accepts invalid email | [Link to screenshot] | Major | Open | Peter Adebisi |
| BUG004 | 13/11/2025 | CheckoutPage | Payment fails silently on network loss | 1. Disconnect network 2. Click 'Pay Now' | User notified of connection issue | Displays "Payment failed to start" without clear cause | [Link to screenshot of error] | Minor | Open | Lena |
| BUG005 | 13/11/2025 | App Routing | User can open /checkout with empty cart | 1. Clear cart 2. Visit /checkout manually | Should redirect user to /catalog | Checkout loads with empty state | [Link to screenshot] | Major | Open | Prifton Mliwa |
| BUG006 | 13/11/2025 | CheckoutPage | Screen reader missing ARIA roles for steps | 1. Open checkout 2. Inspect with screen reader | Each step should have proper ARIA labels | Screen reader reads plain text only | [Link to accessibility audit report] | Minor | Open | Prifton Mliwa |
| BUG007 | 13/11/2025 | CheckoutPage | Order confirmation flashes before redirect | 1. Complete payment 2. Observe redirect | Smooth redirect to /orders/:id | Confirmation flashes briefly | [Link to screen recording] | Cosmetic | Open | Lena |
| BUG008 | 13/11/2025 | Navbar | Search not submitting queries correctly | 1. Enter a book title 2. Press Enter | Should search and filter catalog results | Pressing Enter only redirects to /catalog without using search input | [Link to screen recording] | Major | Open | Peter Adebisi |
| BUG009 | 13/11/2025 | Navbar | Search bar clears unexpectedly after route change | 1. Search a book 2. Navigate to another page 3. Go back | Search term should persist | Search field resets automatically | [Link to screen recording] | Minor | Open | Peter Adebisi |
| BUG010 | 13/11/2025 | Navbar | No debounce for keypress in search | 1. Type quickly in search field | Should handle input efficiently | Input lags and re-renders cause delay | [Link to performance profile/recording] | Minor | Open | Lena |
| BUG011 | 13/11/2025 | Navbar | ESC key not consistently resetting focus | 1. Click in search 2. Press ESC repeatedly | Should clear and refocus search field | Focus sometimes lost and requires manual click | [Link to screen recording] | Minor | Open | Prifton Mliwa |
| BUG012 | 13/11/2025 | Navbar | Cart count badge overlaps icon on mobile | 1. Open app on narrow screen 2. Observe cart icon | Badge should be aligned above icon | Badge overlaps with cart emoji | [Link to screenshot] | Cosmetic | Open | Lena |
| BUG013 | 13/11/2025 | Navbar | Missing ARIA labels on icons | 1. Inspect cart link with screen reader | Should have descriptive ARIA label | Only reads "link" without context | [Link to accessibility tool screenshot] | Minor | Open | Peter Adebisi |
| BUG014 | 13/11/2025 | App.js | 404 redirect loops on invalid URL | 1. Visit /random-page | Should redirect once to /catalog | Rapid redirects flash multiple times | [Link to screen recording] | Minor | Open | Peter Adebisi |
| BUG015 | 13/11/2025 | CheckoutPage | "Back" button from Payment doesn't restore cart data | 1. Proceed to Payment step 2. Click 'Back' | Should retain cart and shipping info | Cart data resets in some cases | [Link to screen recording] | Major | Open | Prifton Mliwa |
---

## 🧾 Summary

| Severity | Count |
|-----------|--------|
| Critical | 1 |
| Major | 5 |
| Minor | 7 |
| Cosmetic | 2 |
| Total | 15 |

---

## 🧠 Notes
- Payment and validation flows require stricter input handling (postal code, email).  
- Accessibility: Add missing ARIA roles and screen reader labels in Navbar and Checkout steps.  
- Performance: Implement debounce for Navbar search input.  
- UI: Fix mobile alignment for cart icon and badge.  
- Routing: Prevent direct navigation to Checkout when cart is empty.

---

Prepared by:  
 LPP TEAM
📅 November 13, 2025  

📁 File: tests/defect-log.md
