# MR YU Regression Checklist

Use this checklist after catalog, configuration, plugin, theme, CSS, checkout or navigation changes. Record Pass, Fail, Blocked or Not Applicable for each item.

## 1. Pre-change controls

- [ ] Current change scope is documented.
- [ ] A recent recoverable backup exists for higher-risk changes.
- [ ] Elementor/Elementor Pro compatibility has been reviewed before any update.
- [ ] Custom code snippets and CSS affected by the change are identified.
- [ ] Validated product IDs, slugs, categories and image filenames are protected.
- [ ] A rollback path is known.
- [ ] Test data contains no customer or payment information.

## 2. Homepage

- [ ] Homepage opens without visible error.
- [ ] Hero content is readable on desktop.
- [ ] Hero content is readable on mobile.
- [ ] Main call-to-action opens the intended destination.
- [ ] Promotional sections display current information.
- [ ] Team and brand sections load correctly.
- [ ] Homepage navigation reaches the menu.
- [ ] Homepage LCP image is not unintentionally lazy-loaded.
- [ ] No new horizontal scroll appears.

## 3. Menu and navigation

- [ ] Menu page opens from the homepage.
- [ ] All intended categories are visible.
- [ ] Category order matches the approved structure.
- [ ] Category controls reach the correct section.
- [ ] Product cards remain aligned.
- [ ] Search is available on desktop.
- [ ] Search works on mobile.
- [ ] Search returns or guides the user to relevant products.
- [ ] A route back to the homepage is available.
- [ ] Account and cart controls remain accessible.

## 4. Product data

For a representative sample from changed and unchanged categories:

- [ ] Product name is correct.
- [ ] Weight or volume is correct.
- [ ] Price is correct.
- [ ] Ingredients are correct.
- [ ] Product image is correct and loads.
- [ ] Product category is correct.
- [ ] Product is visible in the intended menu section.
- [ ] Product page opens.
- [ ] Add-to-cart control is active.
- [ ] Slug and SEO metadata were not unintentionally overwritten.
- [ ] Validated WebP media remains linked.

## 5. Cart and mini-cart

- [ ] Product can be added.
- [ ] Cart count updates.
- [ ] Mini-cart opens.
- [ ] Quantity can be increased.
- [ ] Quantity can be decreased.
- [ ] Quantity change appears without manual refresh.
- [ ] Product can be removed.
- [ ] Line totals are correct.
- [ ] Subtotal is correct.
- [ ] Cart and mini-cart remain synchronized.
- [ ] Free-delivery threshold message recalculates.
- [ ] “Modifică produsele din coș” works.
- [ ] “Mai adaugă un preparat” returns to shopping.
- [ ] Recommended-product images match the products.

## 6. Promotions

- [ ] Valid coupon applies under eligible conditions.
- [ ] Invalid coupon shows a clear message.
- [ ] Minimum-order condition is enforced.
- [ ] Usage limit is enforced where configured.
- [ ] Guest checkout can use eligible public coupons.
- [ ] Discount value is correct.
- [ ] Totals recalculate after coupon removal.
- [ ] Promotional text matches the actual rule.

## 7. Delivery and pickup

- [ ] Delivery can be selected.
- [ ] Pickup can be selected.
- [ ] Switching methods updates fields and fees.
- [ ] Delivery address validation behaves correctly.
- [ ] Pickup does not require irrelevant delivery fields.
- [ ] Free-delivery threshold is applied correctly.
- [ ] Schedule/pre-order behavior is available when intended.
- [ ] Closed-hours messaging does not incorrectly block ordering.
- [ ] Final fulfillment method is visible in the order summary.

## 8. Checkout

- [ ] Guest checkout is available.
- [ ] Login during checkout is available.
- [ ] Registration during checkout is available.
- [ ] Required-field validation is clear.
- [ ] Customer data remains populated after correctable errors.
- [ ] Cart lines match checkout lines.
- [ ] Subtotal, discounts, fees and total are correct.
- [ ] Terms/privacy links open correctly.
- [ ] No large blank jump or broken anchor appears.
- [ ] Mobile keyboard and fields do not hide the main action.

## 9. Customer account

- [ ] My Account shows login.
- [ ] My Account shows registration.
- [ ] New test registration succeeds.
- [ ] Registration email is received.
- [ ] Password setup link opens.
- [ ] Weak-password validation works.
- [ ] Valid password is accepted.
- [ ] Login succeeds.
- [ ] Dashboard opens.
- [ ] Orders opens.
- [ ] Addresses opens.
- [ ] Payment methods opens.
- [ ] Account details opens.
- [ ] Logout succeeds.

## 10. WhatsApp ordering

- [ ] WhatsApp action is visible.
- [ ] Intended destination opens.
- [ ] Generated message contains correct products.
- [ ] Quantities are correct.
- [ ] Subtotal and total are correct.
- [ ] The message contains no unintended personal data.
- [ ] Returning to the website preserves the cart.

## 11. Payment entry points

- [ ] Intended payment methods are visible.
- [ ] Payment method can be selected.
- [ ] Total remains unchanged after selection.
- [ ] External handoff opens only after an intentional action.
- [ ] Cancelling a safe test returns to the correct page.
- [ ] No real transaction is attempted without explicit authorization.
- [ ] Mobile payment controls remain readable and tappable.

## 12. Responsive and browser coverage

### Desktop Chrome

- [ ] Homepage
- [ ] Menu
- [ ] Search
- [ ] Product page
- [ ] Cart
- [ ] Checkout
- [ ] My Account

### Safari on iPhone

- [ ] Homepage
- [ ] Mobile navigation
- [ ] Category controls
- [ ] Search
- [ ] Product page
- [ ] Cart and sticky controls
- [ ] Checkout form
- [ ] My Account

## 13. Post-change review

- [ ] Primary change passes its acceptance criteria.
- [ ] Connected P0/P1 flows pass.
- [ ] No new console-visible or user-visible error is introduced.
- [ ] Cache-sensitive behavior has been checked in a clean session.
- [ ] Remaining risks are documented.
- [ ] Supporting evidence is sanitized.
- [ ] Changelog and timeline are updated.
