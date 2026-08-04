# MR YU – Changelog

This document records verified production improvements, defect fixes and significant QA findings for the MR YU ordering website.

---

## 2026-08-04 – New product listing: Orez cu legume 300 g

### Change implemented

A missing standalone rice side dish was added to the live WooCommerce catalog.

### Product details

- **Product:** Orez cu legume 300 g
- **WooCommerce ID:** 2364
- **Price:** 20 lei
- **Category:** Orez & Garnituri / Orez
- **Ingredients:** Rice, carrot, peas, corn, egg and soy sauce
- **Product URL:** https://mryu.ro/product/orez-cu-legume-300-g/

### Media and SEO

- Main catalog image: WebP, 1200 × 1200 px
- Rank Math SEO score after publication: 74/100

### Validation

Verified successfully:

- direct product page;
- name, weight, price and ingredients;
- main product image;
- intended category assignment;
- active add-to-cart control;
- standalone availability in the online menu.

### Result

**Status: Published and verified**

Detailed session: [2026-08-04 Product Listing](TEST_SESSIONS/2026-08-04-PRODUCT-LISTING.md)

---

## 2026-07-31 – Customer account registration fix

### Issue

The **My Account** page displayed only the login form. New customers had no visible registration option.

A customer also believed that the **BUNVENIT15** voucher required an existing account.

### Confirmed cause

WooCommerce account registration options were disabled.

### Configuration changes

Enabled:

- customer registration on My Account;
- customer registration during checkout;
- customer login during checkout.

Preserved:

- guest checkout;
- automatic username generation;
- password setup via email.

### Validation

Verified successfully:

- registration form;
- registration email;
- password-setup link;
- weak-password validation;
- valid password creation;
- login and logout;
- customer dashboard sections;
- guest coupon use.

### Result

**Status: Fixed and retested**

Detailed defect: [BUG-001](BUG_REPORTS/BUG-001-Customer-Account-Registration.md)

---

## 2026-07-29 – Mini-cart and cart UX improvements

### Changes verified

- Mini-cart subtotal updates in real time.
- “Modifică produsele din coș” shortens the path to cart editing.
- Free-delivery progress calculates the amount remaining to 200 lei.
- “Mai adaugă un preparat” returns customers to shopping.
- Recommended-product image mismatches were corrected.
- Cart quantity changes no longer require manual page refresh.

### Regression focus

- quantity increase and decrease;
- product removal;
- line totals and subtotal;
- free-delivery threshold;
- coupons;
- checkout totals;
- mini-cart synchronization.

### Result

**Status: Implemented and regression-tested**

Detailed defect: [BUG-002](BUG_REPORTS/BUG-002-Cart-Quantity-Update-Required-Refresh.md)

---

## 2026-07-20 – Menu taxonomy and terminology standardized

### Change implemented

The menu structure was reorganized into 14 customer-facing groups covering main dishes, combos, proteins, noodles and rice, soups, sides, desserts, drinks, sauces and promotions.

### Content rule

Product terminology was clarified:

- **Tăiței / noodles** refers to wheat-based noodles.
- **Spaghete** refers to thin rice noodles.

This distinction must be preserved in titles, descriptions, categories and SEO metadata.

### Result

**Status: Structure approved for catalog use**

---

## 2026-07-06 – Homepage LCP performance finding

### Finding

PageSpeed Insights identified that the homepage LCP image:

- used lazy loading;
- did not receive `fetchpriority="high"`;
- was part of a reported critical request chain of approximately 1.449 seconds.

### Result

**Status: Open – requires current-state verification and controlled retest**

Detailed finding: [PERF-001](PERFORMANCE/PERF-001-HOMEPAGE-LCP.md)

---

## 2026-06-29 – Catalog and Rank Math data controls established

### Work completed

A controlled WooCommerce catalog export/import workflow was prepared for product and SEO maintenance.

Protected fields include:

- product IDs;
- slugs;
- prices and stock settings;
- descriptions;
- categories;
- image mappings;
- Rank Math metadata.

Mobile title length and internal product recommendations were included in the content review.

### Result

**Status: Reference data established for controlled catalog updates**
