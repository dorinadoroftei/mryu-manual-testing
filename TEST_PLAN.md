# MR YU Manual Test Plan

## 1. Purpose

This test plan defines the manual QA approach for the MR YU production ordering website. The objective is to protect the customer journey from menu discovery through order submission while documenting defects, usability risks and verified improvements.

## 2. System under test

- **Website:** https://mryu.ro
- **Platform:** WordPress
- **Commerce:** WooCommerce
- **Food-ordering layer:** ExWooFood
- **Environment:** Production
- **Business model:** Delivery and pickup ordering

## 3. Test objectives

- Confirm that customers can discover and select products.
- Verify that product information is accurate and consistent.
- Validate cart calculations and synchronization.
- Verify delivery, pickup, coupon and checkout behavior.
- Confirm that customer-account workflows remain available.
- Check that key flows remain usable on desktop and mobile.
- Detect regressions after configuration, plugin, catalog or design changes.
- Record evidence without exposing personal or payment data.

## 4. In scope

### Catalog

- Menu categories and category order
- Product names, weights, prices and ingredients
- Product images and WebP delivery
- Product visibility
- Add-to-cart controls
- Internal product links
- SEO fields during controlled catalog updates

### Ordering

- Add, remove and change product quantities
- Cart and mini-cart synchronization
- Subtotal and total calculations
- Free-delivery threshold messaging
- Coupons and promotional conditions
- Delivery and pickup selection
- Address collection
- Scheduled/pre-order behavior
- Checkout validation
- WhatsApp ordering entry point
- Payment-method presentation

### Accounts

- Guest checkout
- Registration from My Account
- Registration during checkout
- Login and logout
- Registration email and password setup
- Customer dashboard access

### Experience and compatibility

- Desktop layout
- Responsive mobile layout
- Chrome
- Safari on iPhone
- Navigation and search
- Basic accessibility and usability observations
- Page-load and LCP investigation

## 5. Out of scope

- Destructive testing against production data
- Load or stress testing
- Unauthorized payment attempts
- Access to real customer accounts
- Storage of credentials, card data or private order details
- Blind plugin or theme upgrades
- Source-code security assessment
- Changes to validated product IDs, slugs or media filenames without a controlled import plan

## 6. Risk-based priorities

| Priority | Area | Main risk |
|---|---|---|
| P0 | Checkout and payment entry | Customer cannot complete an order |
| P0 | Cart totals and product quantities | Incorrect order value or quantity |
| P1 | Delivery and pickup | Order cannot be fulfilled correctly |
| P1 | Product availability and add to cart | Customer cannot select an item |
| P1 | Account and guest checkout | Customer onboarding or checkout is blocked |
| P2 | Mobile navigation and search | Product discovery becomes difficult |
| P2 | Promotions and free-delivery messaging | Incorrect commercial expectation |
| P3 | Visual alignment and secondary content | Reduced usability without blocking the order |

## 7. Test environments

### Desktop web

- Google Chrome
- Browser developer tools for responsive and network inspection
- Clean/incognito session where account or cache state matters

### Mobile web

- Safari on iPhone
- Portrait layout
- Mobile navigation, sticky controls, cart and checkout

### Production safeguards

Testing uses low-risk actions. Orders and payments are not finalized unless a controlled business test explicitly requires them. Test accounts and test data must not resemble real customer identities.

## 8. Entry criteria

A test session can start when:

- the affected page is reachable;
- the intended configuration or catalog change has been saved;
- expected behavior is known;
- a safe test path is available;
- relevant backup or rollback protection exists for higher-risk changes.

## 9. Exit criteria

A change can be considered validated when:

- the primary scenario passes;
- connected regression checks pass;
- totals and displayed state remain synchronized;
- desktop and mobile behavior are acceptable where relevant;
- no new P0 or P1 defect is introduced;
- the result and any remaining risk are documented.

## 10. Defect workflow

1. Record the summary and business impact.
2. Capture environment and preconditions.
3. Write reproducible steps.
4. Separate actual and expected results.
5. Assign severity and priority using [QA Standards](QA_STANDARDS.md).
6. Confirm the root cause only when evidence supports it.
7. Retest the correction.
8. Check connected regression areas.
9. Mark the final status and evidence availability.

## 11. Regression triggers

Run targeted regression after:

- WooCommerce or ExWooFood configuration changes;
- plugin, theme or Elementor changes;
- checkout, payment or delivery changes;
- catalog imports;
- product-image replacements;
- menu/category reordering;
- coupon creation or modification;
- homepage or navigation redesign;
- custom CSS or code-snippet changes.

## 12. Known change constraints

- Elementor and Elementor Pro updates require compatibility and license validation before implementation.
- Validated WebP assets must not be replaced without matching the controlled image register.
- Product imports must preserve existing IDs, slugs, prices, categories and SEO fields unless a change is explicitly intended.
- Production changes require a backup and a focused regression pass.
