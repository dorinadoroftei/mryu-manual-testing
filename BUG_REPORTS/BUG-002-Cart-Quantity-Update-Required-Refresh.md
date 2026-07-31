# BUG-002 – Cart Quantity Changes Were Not Updated in Real Time

## Summary

Changing the quantity of a product in the MR YU shopping cart did not immediately update the cart information.

The customer had to refresh/reload the page for the updated state to be reflected correctly.

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
