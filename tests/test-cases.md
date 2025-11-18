# Test Cases
# (Team: LPP team)
# Bookstore Application — Complete Test Cases  
Team: LPP  
Updated: 17 November 2025  

---

### 1. TC-CART-001: Add Item to Cart
*Priority:* High  
*Test Type:* Manual  
*Test Environment:* Android, Chrome browser  
*Pre-conditions:* User is viewing product details page  

*Steps:*
1. Click “Add to Cart” on any book  
2. Observe cart icon in header  
3. Click cart icon  
4. Verify item appears in cart with correct details  

*Expected Result:*
Item is added to cart, cart counter updates, item details are correct

*Evidence:* 
/test/evidence/FR-CART-001.png


---

### 2. TC-CART-002: Update Cart Quantity
*Priority:* High  
*Test Type:* Manual  
*Test Environment:* Android, Chrome browser  
*Pre-conditions:* At least one item in cart  

*Steps:*  
1. Navigate to cart  
2. Locate quantity input  
3. Increase quantity  
4. Verify total updates  
5. Decrease quantity  

*Expected Result:* Total updates according to quantity.  

*Evidence:* 
/test/evidence/FR-CART-002.png

---

### 3. TC-CART-003: Remove Item from Cart  
*Priority:* High  
*Test Type:* Manual  
*Environment:* Android, Chrome  
*Pre-conditions:* Items exist in cart  

*Steps:*  
1. Navigate to cart  
2. Click *Remove*  
3. Confirm  
4. Verify item removed  
5. Check total recalculation  

*Expected Result:* Item fully removed, total recalculated  

*Evidence:*
/test/evidence/FR-CART-003.png

---

### 4. TC-CART-004: Cart Persistence Across Sessions  
*Priority:* Medium  
*Test Type:* Manual  
*Environment:* Android Chrome  
*Pre-conditions:* Items in cart  

*Steps:*  
1. Add items to cart  
2. Close browser  
3. Reopen app  
4. Go to cart  

*Expected Result:* Cart persists via localStorage 

*Evidence:*
/test/evidence/FR-CART-004.png

---

### 5. TC-CART-005: Cart Price Calculation  
*Priority:* High  
*Test Type:* Manual  
*Environment:* Android Chrome  
*Pre-conditions:* Items in cart  

*Steps:*  
1. Add book to cart  
2. Increase quantity to 2  
3. Observe total  

*Expected Result:* Total updates correctly  

*Actual Result:* Works correctly  

*Evidence:*
test/evidence/FR-CART-002.png

---

### 6. TC-CART-006 (from FR-CART-005): Multi-Item Price Calculation  
*Priority:* High  
*Test Type:* Manual  
*Environment:* Browser  
*Pre-conditions:* User has items in cart  

*Steps:*  
1. Add *Lord of the Rings ($19.99)* ×5  
2. Add *The Great Gatsby ($15.99)* ×2  
3. Verify subtotal  

*Expected Result:*  
Correct total:  
(5 × 19.99) + (2 × 15.99) = 131.93  

*Evidence:* 
test/evidence/FR-CART-002.png

---

### 7. TC-CHK-006: Checkout Process Initiation  
*Priority:* High  
*Test Type:* Manual  
*Environment:* Android Chrome  
*Pre-conditions:* Items in cart  

*Steps:*  
1. Open cart  
2. Click *Proceed to Checkout*  
3. Verify checkout page loads  
4. Check items displayed  

*Expected Result:* Checkout loads with items

*Evidence:* 
/test/evidence/FR-CHK-006.png.jpg

---

### 8. TC-CHK-007: Shipping Information Validation  
*Priority:* High  
*Test Type:* Manual  
*Environment:* Android Chrome  
*Pre-conditions:* Checkout page  

*Steps:*  
1. Leave required fields empty  
2. Click Continue  
3. Verify validation messages  

*Expected Result:* Validation prevents continuing  

*Evidence:* 
/test/evidence/FR-CHK-008.jpg


---

### 9. TC-CHK-008 (FR-CHK-003): Paystack Test Payment  
*Priority:* High  
*Test Type:* Manual  
*Environment:* Browser  
*Pre-conditions:* On payment step  

*Steps:*  
1. Enter test card *4084084084084081*  
2. Enter CVV + expiry  
3. Submit  
4. Observe confirmation  

*Expected Result:* Payment succeeds 

*Evidence:* 
/test/evidence/FR-CHK-004.png  

---

### 10. TC-CHK-009 (FR-CHK-004): Currency Mismatch  
*Priority:* High  
*Test Type:* Manual  
*Environment:* Browser  

*Steps:*  
1. Ensure UI shows $  
2. Begin Paystack  
3. Check payment currency  

*Expected Result:* Gateway uses USD 

*Actual Result:* Uses *KES*

*Evidence:* 
/test/evidence/FR-CHK-003.png

---

### 11. TC-CAT-008: Homepage Loads with Product Grid  
*Priority:* High  
*Test Type:* Manual  
*Environment:* Android Chrome  

*Steps:*  
1. Open homepage  
2. Wait for load  
3. Verify product grid  
4. Check multiple books visible  

*Expected Result:* Product grid loads correctly 

*Evidence:* 
/test/evidence/FR-CAT-004.jpg


---

### 12. TC-CAT-009: Product Search Functionality  
*Priority:* Critical  
*Test Type:* Manual  
*Environment:* Android Chrome  

*Steps:*  
1. Search "1984"  
2. Press Enter  
3. Observe results  

*Expected Result:* Only matching books display  

*Actual Result:* One search input works, the other does not  

*Evidence:* 
/test/evidence/FR-CAT-001

---

### 13. TC-CAT-010: Search Options (Title, Author, Description)  
*Priority:* High  
*Test Type:* Manual  

*Steps:*  
1. Search by author  
2. Search by title  
3. Search by description  

*Expected Result:* Correct result per search type 

*Evidence:* 
/test/evidence/FR-CAT-001.png  

---

### 14. TC-CAT-011: Search Results Persistence  
*Priority:* High  
*Test Type:* Manual  

*Steps:*  
1. Search “1984”  
2. Clear input completely  
3. Press Enter  

*Expected Result:* Should show *all* products

*Evidence:
/test/evidence/FR-CAT-003.jpg


---

### 15. TC-CAT-012 (from FR-CAT-001): Search by Title/Author/Description  
*Priority:* High  

*Steps:*  
1. Search “The Great Gatsby”  
2. Observe results  

*Expected Result:* Catalog returns matching book  

*Evidence:* 
/test/evidence/FR-CAT-001.png  

---

### 16. TC-CAT-013 (FR-CAT-002): Catalog Loads All Books  
*Priority:* High  

*Steps:*  
1. Open /catalog  
2. View all books  

*Expected Result:* All books in dataset appear  

*Evidence:* 
/test/evidence/FR-CAT-002.png



---

### 17. TC-ORD-001: Order Confirmation Details  
*Priority:* High  

*Steps:*  
1. Complete purchase  
2. Verify order number  
3. Compare order details  

*Expected Result:* Correct confirmation display  

*Evidence:* 
/test/evidence/FR-ORD-001.png

---

### 18. TC-ORD-002: Order History Access  
*Priority:* Medium  

*Steps:*  
1. Navigate to My Orders  
2. Select order  
3. Review details  

*Expected Result:* Correct history and details  

*Evidence:* 
/test/evidence/FR-ORD-002.png


---

### 19. TC-A11Y-001: Keyboard Navigation  
*Priority:* Medium  

*Steps:*  
1. Use Tab to navigate  
2. Check focus indicators  
3. Use Enter/Space  

*Expected Result:* All elements accessible 

*Evidence:* 
/test/evidence/FR-A11Y-001.png  

---

### 20. TC-A11Y-002: Screen Reader Compatibility  
*Priority:* Medium  

*Steps:*  
1. Enable screen reader  
2. Navigate catalog  
3. Verify alt text & labels  

*Expected Result:* Screen reader reads all content 

*Evidence:* 
/test/evidence/FR-A11Y-002.png  

---

### 21. TC-A11Y-003: Checkout Modal Accessibility  
*Priority:* Medium  

*Steps:*  
1. Run axe audit  
2. Inspect modal  

*Expected Result:* aria-modal="true" + focus trap 

*Actual Result:* Missing / failing  

*Evidence:* 
/test/evidence/FR-A11Y-003.png  


---

### 22. TC-PERF-001: Page Load Performance  
*Priority:* Medium  

*Steps:*  
1. Run Lighthouse  
2. Measure FCP, LCP, etc.  

*Expected Result:* Page loads within 3 seconds

*Evidence:*
/test/evidence/FR-PERF-001.png

---

### 23. TC-PERF-002: Layout Shift (CLS)  
*Priority:* Medium  

*Steps:*  
1. Slow 3G mode  
2. Observe image shifts  

*Expected Result:* No major layout shifts

*Actual Result:* CLS > 0.25 (bad) 

*Evidence:* 
/test/evidence/FR-PERF-002.png  

---

## Catalog & Search Enhancements

### 24. TC-CAT-014: Search with Special Characters
**Priority:** Medium  
**Steps:**
1. Search for "!@#$%"
2. Search for "Harry's"
3. Search for "book-title"
**Expected:** Handles special characters gracefully

**Evidence:** `/test/evidence/FR-CAT-014.png`

---

### 25. TC-CAT-015: Case-Insensitive Search
**Priority:** Medium  
**Steps:**
1. Search "HARRY POTTER" (uppercase)
2. Search "harry potter" (lowercase)
3. Search "Harry Potter" (mixed case)
**Expected:** All return same results

**Evidence:** `/test/evidence/FR-CAT-015.png`

---

### 26. TC-CAT-016: Empty Search Results
**Priority:** Medium  
**Steps:**
1. Search for "xyz123nonexistent"
2. Verify "No results found" message
3. Check if suggestions appear
**Expected:** Clear empty state message

**Evidence:** `/test/evidence/FR-CAT-016.png`

---

### 27. TC-CAT-017: Search Persistence on Navigation
**Priority:** Low  
**Steps:**
1. Search "1984"
2. Navigate to cart
3. Return to catalog
**Expected:** Search results maintained or cleared (document which)

**Evidence:** `/test/evidence/FR-CAT-017.png`

---

## Cart Enhancements

### 28. TC-CART-007: Maximum Quantity Limit
**Priority:** High  
**Steps:**
1. Add item to cart
2. Try to increase quantity to 1000
3. Check if there's a maximum limit
**Expected:** Reasonable quantity limit enforced

**Evidence:** `/test/evidence/FR-CART-007.png`

---

### 29. TC-CART-008: Add Same Item Multiple Times
**Priority:** High  
**Steps:**
1. Add "Harry Potter" to cart
2. Navigate away and add same book again
3. Check if quantity increases vs. duplicate entry
**Expected:** Quantity increments, no duplicates

**Evidence:** `/test/evidence/FR-CART-008.png`

---

### 30. TC-CART-009: Cart Badge Updates
**Priority:** Medium  
**Steps:**
1. Add 3 different books
2. Remove 1 book
3. Verify cart badge shows correct count (2)
**Expected:** Badge accurately reflects total items

**Evidence:** `/test/evidence/FR-CART-009.png`

---

### 31. TC-CART-010: Cart Across Browser Tabs
**Priority:** Medium  
**Steps:**
1. Add item in Tab 1
2. Open new tab with same site
3. Check if cart syncs between tabs
**Expected:** Cart state consistent across tabs

**Evidence:** `/test/evidence/FR-CART-010.png`

---

## Responsive Design Tests

### 32. TC-RESP-001: Mobile Navigation
**Priority:** Medium  
**Environment:** Mobile Chrome  
**Steps:**
1. Open on mobile
2. Test hamburger menu
3. Verify touch targets (min 44px)
**Expected:** Mobile navigation works smoothly

**Evidence:** `/test/evidence/FR-RESP-001.png`

---

### 33. TC-RESP-002: Tablet Layout
**Priority:** Low  
**Environment:** Tablet  
**Steps:**
1. Test on tablet size
2. Check catalog grid (2-3 columns)
3. Verify readable text sizes
**Expected:** Optimized tablet layout

**Evidence:** `/test/evidence/FR-RESP-002.png`

---

### 34. TC-RESP-003: Small Mobile (320px)
**Priority:** Medium  
**Steps:**
1. Resize to 320px width
2. Check for horizontal scrolling
3. Verify buttons still clickable
**Expected:** No layout breaks on small screens

**Evidence:** `/test/evidence/FR-RESP-003.png`

---



