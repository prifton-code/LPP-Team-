# 🐞 Bookstore App — Defect Log (Week 2)
Team: LPP Team  
Project: Bookstore Web Application  
Phase: Week 2 — Test Design & Early Execution  
Date: November 13, 2025  
Prepared by: LPP Team  

---

## 🧩 Overview
This defect log documents bugs and usability issues detected during Week 2 testing of the Bookstore App.  
Testing covered routing, navigation, checkout workflow, and accessibility of major components.

---

# Defect Log – Bookstore Project App

---

## BUG 001
*Component:* Checkout  
*Summary:* UI shows USD ($) while payment gateway uses KES  
*Steps to Reproduce:*  
1. Open any product page.  
2. Observe displayed price.  
3. Proceed to checkout and view payment gateway.  
*Expected Result:* Currency should match across UI and gateway.  
*Actual Result:* UI uses USD; gateway uses KES.  
*Severity:* High  
*Priority:* High  
*Status:* Open  
*Assignee:* Lena

---

## BUG 002
*Component:* Cart  
*Summary:* Rounding inconsistencies between line totals and grand total  
*Steps to Reproduce:*  
1. Add multiple books with decimal pricing.  
2. Compare line totals vs final grand total.  
*Expected Result:* All totals must be consistently rounded.  
*Actual Result:* Differences occur due to inconsistent rounding.  
*Severity:* Medium  
*Priority:* Medium  
*Status:* Open  
*Assignee:* Prifton

---

## BUG 003
*Component:* Returns Module  
*Summary:* System incorrectly accepts returns on Day 8  
*Steps to Reproduce:*  
1. Purchase an item.  
2. Attempt a return 8 days after order date.  
*Expected Result:* System should reject returns after Day 7.  
*Actual Result:* Return is accepted on Day 8.  
*Severity:* Medium  
*Priority:* Medium  
*Status:* Open  
*Assignee:* Peter 

---

## BUG 004
*Component:* Markdown / Reviews  
*Summary:* XSS allowed via javascript: markdown link  
*Steps to Reproduce:*  
1. Submit review with: [test](javascript:alert('XSS')).  
2. View rendered review.  
*Expected Result:* Unsafe URL schemes blocked.  
*Actual Result:* Browser executes JavaScript.  
*Severity:* Critical  
*Priority:* Critical  
*Status:* Open  
*Assignee:* Peter

---

## BUG 005
*Component:* Mini-Cart  
*Summary:* User can exceed available stock due to race condition  
*Steps to Reproduce:*  
1. Add item with low stock.  
2. Rapidly increase quantity in mini-cart.  
*Expected Result:* Quantity capped at stock limit.  
*Actual Result:* Quantity exceeds available stock.  
*Severity:* High  
*Priority:* High  
*Status:* Open  
*Assignee:* Lena 

---

## BUG 006
*Component:* Checkout Modal (A11y)  
*Summary:* Missing aria-modal and no focus restoration  
*Steps to Reproduce:*  
1. Open checkout modal.  
2. Navigate with keyboard or screen reader.  
3. Close modal.  
*Expected Result:* Modal traps focus and returns to trigger element.  
*Actual Result:* Focus moves unpredictably.  
*Severity:* Medium  
*Priority:* Low  
*Status:* Open  
*Assignee:* Prifton

---

## BUG 007
*Component:* CSV Export  
*Summary:* CSV uses decimal comma instead of decimal point  
*Steps to Reproduce:*  
1. Export CSV with numeric fields.  
2. Open in Excel / Google Sheets.  
*Expected Result:* Standard decimal point formatting.  
*Actual Result:* Uses decimal comma, breaking parsing.  
*Severity:* Low  
*Priority:* Low  
*Status:* Open  
*Assignee:* Peter  

---

## BUG 008
*Component:* Notifications  
*Summary:* Notification badge not updated after "Mark all read"  
*Steps to Reproduce:*  
1. Open notifications panel.  
2. Click "Mark all read".  
*Expected Result:* Badge resets to 0.  
*Actual Result:* Badge still shows unread count.  
*Severity:* Low  
*Priority:* Medium  
*Status:* Open  
*Assignee:* Lena

---

## BUG 009
*Component:* Image Loading / Performance  
*Summary:* Non-lazy images causing slow page load  
*Steps to Reproduce:*  
1. Load homepage or catalog on mobile.  
2. Observe image loading behavior.  
*Expected Result:* Images should load lazily.  
*Actual Result:* All images load instantly, impacting performance.  
*Severity:* Medium  
*Priority:* Low  
*Status:* Open  
*Assignee:* Peter

---

## BUG 010
*Component:* Search  
*Summary:* Search ignores diacritics  
*Steps to Reproduce:*  
1. Search “Jose”.  
2. Observe missing results for “José”.  
*Expected Result:* Search normalization should match accented characters.  
*Actual Result:* No results returned.  
*Severity:* Low  
*Priority:* Low  
*Status:* Open  
*Assignee:* Lena

---

## BUG 011
*Component:* Orders / Payment Success  
*Summary:* Duplicate orders created due to double state insertion  
*Steps to Reproduce:*  
1. Proceed through checkout.  
2. Complete payment successfully.  
3. Check order history.  
*Expected Result:* Only one order appears.  
*Actual Result:* Order duplicated.  
*Severity:* High  
*Priority:* High  
*Status:* Open  
*Assignee:* Checkout Dev  
*Evidence:* Two identical orders appear.

---

## BUG 012
*Component:* State Management  
*Summary:* Stale orders state used in callback  
*Steps to Reproduce:*  
1. Perform multiple checkouts quickly.  
2. Check order state.  
*Expected Result:* State updates should use latest values.  
*Actual Result:* Overwritten or missing entries.  
*Severity:* Medium  
*Priority:* Medium  
*Status:* Open  
*Assignee:* Prifton

---

## BUG 013
*Component:* Checkout Navigation  
*Summary:* User can navigate back to payment after success  
*Steps to Reproduce:*  
1. Complete payment.  
2. On confirmation page, press browser back.  
*Expected Result:* Should not return to payment page.  
*Actual Result:* Loads payment step again.  
*Severity:* Medium  
*Priority:* Medium  
*Status:* Open  
*Assignee:* Lena

---

## BUG 014
*Component:* Shipping Form  
*Summary:* Weak email validation allows invalid addresses  
*Steps to Reproduce:*  
1. Enter “a@b” as email.  
2. Submit.  
*Expected Result:* Stronger validation should block short domain.  
*Actual Result:* Form accepts invalid email.  
*Severity:* Low  
*Priority:* Low  
*Status:* Open  
*Assignee:* Lena

---

## BUG 015
*Component:* Checkout Cart Validation  
*Summary:* Checkout allows empty cart when transitioning steps  
*Steps to Reproduce:*  
1. Start checkout with items in cart.  
2. Remove all items using another browser tab.  
3. Continue in existing checkout tab.  
*Expected Result:* Should stop user when cart is empty.  
*Actual Result:* User continues with empty cart.  
*Severity:* High  
*Priority:* Medium  
*Status:* Open  
*Assignee:* Peter

---

## BUG 016
*Component:* Payment  
*Summary:* No timeout handling if payment gateway hangs  
*Steps to Reproduce:*  
1. Start payment.  
2. Simulate hanging gateway.  
*Expected Result:* Should show timeout error after X seconds.  
*Actual Result:* UI stays stuck on “Processing…” indefinitely.  
*Severity:* High  
*Priority:* Medium  
*Status:* Open  
*Assignee:* Peter

---

## BUG 017
*Component:* Order Details  
*Summary:* Missing book image breaks layout  
*Steps to Reproduce:*  
1. Create order with missing book.image.  
2. Open order details.  
*Expected Result:* Should fallback to placeholder image.  
*Actual Result:* UI breaks or shows broken image icon.  
*Severity:* Medium  
*Priority:* Low  
*Status:* Open  
*Assignee:* Prifton

---

## BUG 018
*Component:* Order Status  
*Summary:* Unknown status values break status progress calculation  
*Steps to Reproduce:*  
1. Create an order with custom status.  
2. Open order details.  
*Expected Result:* App should handle unknown statuses gracefully.  
*Actual Result:* Progress bar resets incorrectly to first step.  
*Severity:* Medium  
*Priority:* Low  
*Status:* Open  
*Assignee:* Prifton

---

## BUG 019
*Component:* Shipping Form  
*Summary:* Postal code & country fields accept invalid formats  
*Steps to Reproduce:*  
1. Enter “&&&” as postal code.  
2. Enter “Earth” as country.  
3. Submit.  
*Expected Result:* Validation should reject invalid formats.  
*Actual Result:* Form accepts all values.  
*Severity:* Low  
*Priority:* Low  
*Status:* Open  
*Assignee:* Lena

---

## BUG 020
*Component:* Order ID Generation  
*Summary:* Time-based IDs (Date.now()) can collide  
*Steps to Reproduce:*  
1. Submit two orders almost simultaneously.  
2. Check order list.  
*Expected Result:* Each order should have a unique ID.  
*Actual Result:* Same ID is generated in rare cases.  
*Severity:* High  
*Priority:* Medium  
*Status:* Open  
*Assignee:* Peter

---

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