# MR YU Core Regression Test Cases

These reusable manual test cases cover the customer-critical workflows of the MR YU ordering website.

## Test-case conventions

- **Environment:** Production, unless stated otherwise
- **Data:** Public product data and anonymized test information
- **Result:** Record as Pass, Fail, Blocked or Not Run
- **Evidence:** Capture only sanitized screenshots or notes

---

## TC-001 – Browse menu categories

**Priority:** High  
**Type:** Functional / UI / Responsive

### Preconditions

- The website is available.
- No customer login is required.

### Steps

1. Open the homepage.
2. Navigate to the menu.
3. Review the visible category controls.
4. Open several categories.
5. Scroll between category sections.
6. Repeat in a mobile viewport.

### Expected result

- Menu navigation is visible and usable.
- Each category opens or scrolls to the intended section.
- Product cards remain readable.
- No category control covers important page content.
- Mobile category navigation remains accessible.

---

## TC-002 – Validate product-card and product-page data

**Priority:** High  
**Type:** Functional / Content

### Preconditions

- A published product is available in the menu.

### Steps

1. Locate the product in its intended category.
2. Review its card.
3. Open the product page.
4. Compare name, weight, price, description and image.
5. Confirm that the add-to-cart control is available.

### Expected result

- Product data is consistent across the menu and product page.
- The main image loads without distortion.
- The product belongs to the intended category.
- The correct price is displayed.
- The add-to-cart control is active.

---

## TC-003 – Add product and synchronize cart state

**Priority:** Critical  
**Type:** Functional / Regression

### Preconditions

- At least one product is available for ordering.
- The cart is empty.

### Steps

1. Add a product to the cart.
2. Open the mini-cart or cart.
3. Increase the quantity.
4. Decrease the quantity.
5. Add a second product.
6. Remove one product.
7. Compare line totals, subtotal and cart indicator.
8. Continue to checkout.

### Expected result

- Cart state updates without manual page refresh.
- Product quantities remain correct.
- Removed products disappear immediately.
- Cart indicator, mini-cart, cart and checkout stay synchronized.
- Subtotal and total calculations are correct.

**Traceability:** [BUG-002](../BUG_REPORTS/BUG-002-Cart-Quantity-Update-Required-Refresh.md)

---

## TC-004 – Validate delivery checkout

**Priority:** Critical  
**Type:** End-to-end / Functional

### Preconditions

- Products are present in the cart.
- Delivery is available for the test area.

### Steps

1. Continue from cart to checkout.
2. Select delivery.
3. Enter anonymized valid customer data.
4. Enter a supported delivery address.
5. Review fees and order total.
6. Review available payment methods.
7. Stop before final submission unless the business has authorized a controlled test order.

### Expected result

- Required fields are clear.
- Valid address data is accepted.
- Delivery cost and total are displayed correctly.
- Available payment methods can be selected.
- The order summary matches the cart.

---

## TC-005 – Validate pickup checkout

**Priority:** High  
**Type:** End-to-end / Functional

### Preconditions

- Products are present in the cart.
- Pickup is available.

### Steps

1. Continue to checkout.
2. Select pickup.
3. Review the fields and fees.
4. Enter anonymized valid customer details.
5. Review the order summary.
6. Stop before final submission unless authorized.

### Expected result

- Pickup can be selected independently of delivery.
- Delivery-only fields or charges are not incorrectly required.
- The correct total is shown.
- Order details remain consistent.

---

## TC-006 – Apply a promotional code during guest checkout

**Priority:** High  
**Type:** Functional / Business rules

### Preconditions

- A valid public test promotion is available.
- The customer is logged out.
- Cart conditions satisfy the promotion.

### Steps

1. Add eligible products to the cart.
2. Continue as a guest.
3. Open the coupon field.
4. Enter the valid code.
5. Review the discount.
6. Repeat with an invalid code.
7. Change the cart so minimum conditions are not met.

### Expected result

- A valid code applies without requiring account registration unless the promotion explicitly says otherwise.
- The discount amount is correct.
- Invalid or ineligible codes show a clear message.
- Totals recalculate after cart changes.

**Related finding:** BUNVENIT15 was verified as usable without an account.

---

## TC-007 – Register a customer account

**Priority:** High  
**Type:** Functional / Regression

### Preconditions

- The visitor is logged out.
- A safe, unused test email is available.

### Steps

1. Open the My Account page.
2. Confirm that registration is visible.
3. Submit the test email.
4. Open the registration email.
5. Follow the password-setup link.
6. Test weak-password validation.
7. Set a valid password.
8. Log in.
9. Review dashboard sections.
10. Log out.

### Expected result

- Login and registration options are available.
- Registration email is received.
- Password validation behaves consistently.
- The new account can log in.
- Orders, Addresses, Payment methods and Account details are accessible.
- Logout succeeds.

**Traceability:** [BUG-001](../BUG_REPORTS/BUG-001-Customer-Account-Registration.md)

---

## TC-008 – Validate WhatsApp ordering entry point

**Priority:** High  
**Type:** Functional / Integration

### Preconditions

- One or more products are in the cart.
- WhatsApp or WhatsApp Web is available.

### Steps

1. Open the cart options.
2. Select the WhatsApp-ordering action.
3. Review the generated message before sending.
4. Compare products, quantities and totals with the cart.

### Expected result

- The intended WhatsApp destination opens.
- The message contains the correct products, quantities and totals.
- No unrelated customer data is inserted.
- The customer can return to the website without losing the cart.

---

## TC-009 – Validate payment-method presentation

**Priority:** Critical  
**Type:** Functional / Integration

### Preconditions

- Checkout contains valid cart and customer data.
- No real payment is required for the presentation check.

### Steps

1. Reach the payment step for delivery.
2. Record the available methods.
3. Select each method without authorizing a transaction.
4. Review validation and external handoff behavior where safe.
5. Repeat on mobile.

### Expected result

- Intended payment methods are visible.
- Only one method is selected at a time.
- The order total does not change unexpectedly.
- Mobile controls remain usable.
- Any unavailable method provides a clear explanation.

---

## TC-010 – Validate ordering outside normal opening hours

**Priority:** High  
**Type:** Functional / Business rules

### Preconditions

- The restaurant is outside its current opening window.
- Pre-ordering is intended to remain available.

### Steps

1. Open a product page.
2. Add the product to the cart.
3. Continue to checkout.
4. Review scheduling or next-available-time messaging.
5. Verify that the user is not incorrectly blocked by the closed state.

### Expected result

- Products can be added when pre-ordering is enabled.
- The customer receives accurate scheduling guidance.
- Closing status does not silently disable the complete ordering flow.

---

## TC-011 – Validate mobile navigation and persistent controls

**Priority:** High  
**Type:** Responsive / Usability

### Preconditions

- Use Safari on iPhone or a representative mobile viewport.

### Steps

1. Open the homepage in portrait mode.
2. Navigate to the menu.
3. Use category controls and search.
4. Add a product.
5. Open the cart.
6. Return to the homepage.
7. Continue to checkout.

### Expected result

- Logo, menu, search, account and cart controls are visible or discoverable.
- Sticky controls do not hide content or buttons.
- Cart count is readable.
- Text and images do not overflow.
- The customer can return to the homepage from inner pages.

---

## TC-012 – Validate a newly published catalog item

**Priority:** High  
**Type:** Catalog / Smoke test

### Preconditions

- The product has been created and published.
- The main image and SEO fields have been saved.

### Steps

1. Open the direct product URL.
2. Locate the item in its menu category.
3. Verify name, weight, price, ingredients and image.
4. Confirm category assignment.
5. Add the item to the cart.
6. Review the cart line item.
7. Review SEO title, slug and metadata in the administration area.

### Expected result

- The product is publicly reachable.
- Catalog and product-page data are consistent.
- The product can be added to the cart.
- Existing product IDs, slugs and validated media are unaffected.

**Executed example:** “Orez cu legume 300 g” was published and verified on 2026-08-04.
