# BUG-002 – Cart Quantity Changes Were Not Updated in Real Time

## Summary

Changing the quantity of a product in the MR YU shopping cart did not immediately update the cart information.

The customer had to refresh/reload the page for the updated state to be reflected correctly.

---

## Business Impact

Customers could lose confidence in the cart, continue with an outdated quantity or total, or abandon checkout because the interface appeared unresponsive.

A manual page refresh was available as a workaround, so ordering was impaired but not completely blocked.

---

## Module

Shopping Cart / WooCommerce

---

## Environment

- Website: MR YU
- Platform: WordPress
- E-commerce: WooCommerce
- Food ordering functionality: ExWooFood
- Environment: Production
- Device scope: Desktop and responsive web
- Date resolved: July 2026

---

## Preconditions

- At least one product has been added to the shopping cart.
- The cart page or cart interface is accessible.

---

## Steps to Reproduce

1. Open the MR YU website.
2. Add a product to the cart.
3. Open the shopping cart.
4. Change the quantity of the product.
5. Observe the cart without manually refreshing the page.

---

## Actual Result

The cart did not immediately reflect the quantity change.

A manual page refresh was required before the customer could reliably see the updated cart state.

---

## Expected Result

Changing the product quantity should automatically update the cart without requiring the customer to reload the page.

The updated cart information should be displayed immediately.

---

## Severity

**Major**

The issue affected a core e-commerce function immediately before checkout.

---

## Priority

**High**

Cart interactions should be reliable and provide immediate feedback to customers.

---

## Root Cause

**Not confirmed**

The visible behavior and the successful correction were verified, but the available evidence did not identify the exact technical cause. No plugin, script or configuration is presented as the cause without supporting evidence.

---

## Resolution

The cart behavior was modified so quantity changes are reflected without requiring a manual page refresh.

---

## Retesting

The cart was tested again after the modification.

Verified:

- Product quantity could be changed.
- The change was reflected without manual refresh.
- The customer could continue the ordering flow using the updated cart state.

---

## Status

**Fixed and retested**

---

## Evidence Available

- Reproduction notes describing the stale cart state.
- Manual before/after behavior comparison.
- Retest observations for quantity changes and checkout continuation.

No customer or payment information is required for this evidence.

---

## Regression Areas

Related functionality to monitor after the fix:

- Add to cart
- Remove from cart
- Quantity increase
- Quantity decrease
- Cart totals
- Coupon application
- Checkout transition

---

## QA Conclusion

The issue affected usability and reliability of the shopping cart.

After the modification, quantity changes were reflected without requiring the customer to manually reload the page.
---

## Interview Discussion

### Possible interview questions

**1. How did you reproduce this issue?**

I added a product to the shopping cart, changed the quantity and observed the cart without manually refreshing the page. The updated state was not reflected immediately.

**2. Why was the severity classified as Major?**

The issue affected a core e-commerce function immediately before checkout. Although the customer could use a page refresh as a workaround, the cart state was not reliable and could create uncertainty about quantities and totals.

**3. Why was the root cause not documented?**

The available evidence confirmed the visible behavior and the successful fix, but it did not confirm the exact technical cause. I avoided documenting an assumption as a verified root cause.

**4. How did you verify the fix?**

I changed product quantities again and confirmed that the cart updated without a manual refresh. I also checked that the customer could continue to checkout using the updated cart state.

**5. What additional checks should be performed after this type of fix?**

I would verify:

- quantity increase;
- quantity decrease;
- product removal;
- cart totals;
- delivery threshold;
- coupon application;
- checkout totals;
- mini-cart synchronization.

**6. What risks could remain after the fix?**

The cart interface may update visually while totals or checkout data remain outdated. For this reason, both the displayed cart and the final checkout values must be validated.

**7. What business impact could this issue have caused?**

Customers could lose confidence in the cart, place an order with the wrong quantity or abandon the ordering process because the interface appeared unresponsive.

### Key lesson

A successful UI update is not enough. After a cart-related fix, the product quantity, totals, discounts, delivery conditions and checkout data must all remain synchronized.
