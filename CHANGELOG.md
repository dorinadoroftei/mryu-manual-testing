# MR YU - Changelog

This document contains the chronological history of functional improvements, bug fixes, testing activities and usability enhancements performed during the manual testing of the MR YU restaurant website.

---

## 2026-08-04 – New Product Listing: Orez cu legume 300 g

### Change Implemented

A missing standalone rice side dish was added to the live WooCommerce catalog.

### Product Details

- **Product:** Orez cu legume 300 g
- **WooCommerce ID:** 2364
- **Price:** 20 lei
- **Category:** Orez & Garnituri / Orez
- **Ingredients:** rice, carrot, peas, corn, egg and soy sauce
- **Product URL:** https://mryu.ro/product/orez-cu-legume-300-g/

### Media and SEO

- Main catalog image exported as WebP, 1200 × 1200 px.
- Rank Math SEO score after publication: 74/100.

### Functional Testing

The following checks were completed successfully:

- Product page opens correctly.
- Product name, weight, price and ingredients are displayed.
- Main product image loads correctly.
- Product is assigned to the intended catalog categories.
- The **Add to cart** button is active.

### Result

**Status:** ✅ Published and verified

The product is now available as a standalone item in the MR YU online menu.

---

## 2026-07-31 – Customer Account Registration Fix

### Issue Reported

A customer reported that the **My Account** page displayed only the login form and did not provide the possibility to create a new customer account.

The customer also believed that the **BUNVENIT15** voucher could only be used after logging into an existing account.

---

### Root Cause

WooCommerce account registration options had been disabled.

As a result:

- New customers could not create an account.
- Existing users who believed they had an account had no registration alternative.
- The registration form was hidden from the **My Account** page.

---

### Configuration Changes

Enabled:

- Customer registration on **My Account** page.
- Customer registration during Checkout.
- Customer login during Checkout.

Kept enabled:

- Automatic username generation.
- Password setup via email.

---

### Functional Testing

The following scenarios were successfully verified:

- Customer registration.
- Registration email delivery.
- Password creation link.
- Password policy validation.
- Login with newly created credentials.
- Dashboard accessibility.
- Orders section.
- Addresses section.
- Payment methods section.
- Account details section.

---

### Security Testing

Password validation correctly rejected:

- Empty password.
- Weak password.
- Password without uppercase letter.
- Password without numeric character.
- Password without special character.

Password creation was only allowed after all security requirements were satisfied.

---

### Additional Finding

Testing confirmed that the **BUNVENIT15** promotional voucher **does not require a customer account**.

The voucher can be applied directly during Checkout using the **Coupon Code** field.

---

### Result

**Status:** ✅ Fixed

The complete customer registration workflow has been restored and successfully validated.

---

### QA Notes

This issue was discovered after a real customer report and reproduced successfully.

The complete workflow was analysed, corrected, tested and documented.

The fix improves customer onboarding and reduces the risk of losing direct online orders.
