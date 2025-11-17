### TC-CART-001: Add Item to Cart
**Priority:** high
**Test Type:** Manual
**Test environment:** android, chrome browser 
**Pre-conditions:** User is viewing product details page
**Steps:**
1. Click "Add to Cart" button on any book
2. Observe cart icon in header
3. Click on cart icon to view cart
4. Verify item appears in cart with correct details
**Expected Result:**
Item is added to cart, cart counter updates, item details are correct
**Evidence:** `
Screenshot_20251117-103020.jpg
---
### TC-CART-002: Update Cart Quantity
**Priority:**  High
**Test Type:** Manual
**Test environment:** android, chrome browser 
**Pre-conditions:** User has at least one item in cart
**Steps:**
1. Navigate to cart page
2. Locate quantity input for an item
3. Increase quantity by editing the number or click the item twice or according to quantity needed
4. Verify total price updates correctly
5. Decrease quantity by editing the number button
**Expected Result:** Quantity changes reflect in cart total price calculation
**Evidence:**


---
### TC-CART-003: Remove Item from Cart
**Priority:** High
**Test Type:** Manual
**Test environment:** android, chrome browser 
**Pre-conditions:** User has items in cart
**Steps:**
1. Navigate to cart page
2. Click "Remove" button next to an item
3. Confirm removal if prompted
4. Verify item is removed from cart
5. Check cart total updates correctly
**Expected Result:** Item is completely removed from cart, total price recalculated
**Evidence:**


---
### TC-CART-004: Cart Persistence Across Sessions
**Priority:** Medium
**Test Type:** Manual
**Test environment:** android, chrome browser 
**Pre-conditions:** User has items in cart
**Steps:**
1. Add items to cart
2. Close browser tab
3. Reopen application in new tab
4. Navigate to cart page
**Expected Result:** Cart items persist across browser sessions via localStorage
**Evidence:**


---
### TC-CART-005: Cart  Price Calculation
**Priority:**  High
**Test Type:** Manual
**Pre-conditions:** User has items in cart
**Steps:**
1. Add any book in the catalog to cart 
2. Navigate to cart page
3. Click to increase quantity to 2
4. Observe total price calculation
**Expected Result:** Total price should update accordingly 
**Actual Result:** Total price updates accordingly 
**Evidence:**


---

### TC-CHK-006: Checkout Process Initiation
**Priority:** High
**Test Type:** Manual
**Test environment:** android, chrome browser 
**Pre-conditions:** User has items in cart
**Steps:**
1. Navigate to cart page
2. Click "Proceed to Checkout" button
3. Verify checkout page loads
4. Check that cart items are displayed in checkout
**Expected Result:** Checkout process starts successfully, all cart items visible
**Evidence:**



---
### TC-CHK-007: Shipping Information Form Validation
**Priority:**  High
**Test Type:** Manual
**Test environment:** android, chrome browser 
**Pre-conditions:** User is on checkout page
**Steps:**
1. Leave required fields empty
2. Click "Continue to Payment"
3. Verify validation messages appear
**Expected Result:** Form validation prevents proceeding with invalid data/empty field
**Evidence:**


---
### TC-CAT-008: Homepage Loads with Product Grid
**Priority:** high
**Test Type:** Manual
**Test environment:** android, Chrome browser 
**Pre-conditions:** User accesses application URL
**Steps:**
1. Navigate to application homepage
2. Wait for page to fully load
3. Verify product grid is displayed
4. Check that multiple book products are visible
**Expected Result:** Homepage displays grid of book products with images, titles, and prices
**Evidence:**


---
### TC-CAT-009: Product Search Functionality
**Priority:**  Critical
**Test Type:** Manual
**Test environment:** android, chrome browser 
**Pre-conditions:** User is on homepage, catalog is loaded
**Steps:**
1. Locate search input field
2. Enter search term "1984"
3. Click search button or press Enter
4. Observe search results
**Expected Result:** Only books containing "1984" in title/author/description are displayed
**Actual Result:** one search input works perfectly while the other doesn't not
**Evidence:**



---
### TC-CAT-010: Product search options
**Priority:**  High
**Test Type:** Manual
**Test environment:** Android, chrome browser 
**Pre-conditions:** User is on catalog page with multiple book categories
**Steps:**
1. search input field search by author, 
2. Verify only author searched book is displayed
3. search input field search by book title 
4. Verify only title searched book is displayed
5. search input field search by book description
6. Verify only searched book description is displayed
**Expected Result:** search options of Book title, Author and Book description works accordingly 
**Evidence:**




---
### TC-CAT-011: Search Results Persistence 
**Priority:** High
**Test Type:** Manual
**Test environment:** Android, chromr browser 
**Pre-conditions:** User has performed a search
**Steps:**
1. Search for "1984" - results display correctly
2. Clear the search input completely using backspace
3. Press Enter or click search icon
**Expected Result:** Should display all products (clear search filter)
**Evidence:**


