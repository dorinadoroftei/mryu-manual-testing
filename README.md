# Production QA Portfolio – MR YU Case Study

## Project overview

This repository documents hands-on manual QA work completed for [mryu.ro](https://mryu.ro), a live restaurant ordering website built with WordPress, WooCommerce and ExWooFood.

The portfolio focuses on real production workflows: catalog browsing, responsive navigation, cart behavior, checkout, delivery and pickup, promotional codes, customer accounts, WhatsApp ordering and payment entry points.

> This is a QA case study and documentation repository. It is not the source-code repository or a backup of the live WordPress website.

## Project status

- **Environment:** Live production website
- **Testing type:** Manual, exploratory, regression and risk-based testing
- **Primary platforms:** Desktop web and responsive mobile web
- **Last documentation update:** 2026-08-04
- **Current documented defects:** 2 fixed, 1 performance finding awaiting retest

## Testing scope

- Functional testing
- UI and usability testing
- Responsive testing
- Cart and checkout testing
- Delivery and pickup validation
- Payment-flow validation
- Cross-browser testing
- Regression testing
- Exploratory testing
- Catalog and product-data validation
- Basic performance investigation

## Areas tested

- Product menu and category navigation
- Product pages and product data
- Shopping cart and mini-cart
- Checkout process
- Delivery and pickup options
- Promotional codes
- Customer registration and login
- WhatsApp ordering
- Payment methods
- Mobile navigation and responsive layout
- Homepage and menu performance

## Repository map

| Document | Purpose |
|---|---|
| [Test Plan](TEST_PLAN.md) | Objectives, scope, risks, environments and test approach |
| [Core Test Cases](TEST_CASES/CORE-FLOWS.md) | Reusable end-to-end regression scenarios |
| [Regression Checklist](CHECKLISTS/REGRESSION-CHECKLIST.md) | Release and change-validation checklist |
| [Project Timeline](PROJECT_TIMELINE.md) | Chronological view of the QA work |
| [Changelog](CHANGELOG.md) | Verified fixes and production improvements |
| [QA Standards](QA_STANDARDS.md) | Severity, priority and documentation rules |
| [BUG-001](BUG_REPORTS/BUG-001-Customer-Account-Registration.md) | Missing customer registration workflow |
| [BUG-002](BUG_REPORTS/BUG-002-Cart-Quantity-Update-Required-Refresh.md) | Cart quantity required manual refresh |
| [PERF-001](PERFORMANCE/PERF-001-HOMEPAGE-LCP.md) | Homepage LCP image loaded with low priority |
| [Product Listing Session](TEST_SESSIONS/2026-08-04-PRODUCT-LISTING.md) | Validation of “Orez cu legume 300 g” |

## Highlighted results

### Customer registration restored

A real customer report revealed that the **My Account** page offered login only. The WooCommerce account settings were reviewed, registration was restored and the complete email/password/login workflow was retested.

### Cart feedback improved

A cart defect required customers to refresh the page after changing quantities. The corrected flow was retested, including quantity changes, totals and transition to checkout.

### Catalog quality controlled

Product updates were checked for names, weights, prices, ingredients, categories, images, add-to-cart behavior and Rank Math metadata. Validated product IDs, slugs and WebP assets were preserved during catalog work.

### Performance risk documented

A PageSpeed review identified that the homepage LCP image was lazy-loaded and did not receive high fetch priority. The finding is documented separately and remains subject to controlled implementation and retesting.

## Test approach

1. Reproduce the customer or business-reported behavior.
2. Record the environment, preconditions and exact steps.
3. Separate confirmed facts from assumptions.
4. Classify business impact using the repository QA standards.
5. Verify the correction in the affected flow.
6. Run targeted regression checks on connected workflows.
7. Document the result without exposing customer or payment data.

## Tools used

- Chrome DevTools
- Google Chrome
- Safari on iPhone
- PageSpeed Insights
- Microsoft Excel
- GitHub
- WordPress
- WooCommerce
- Rank Math SEO

## Data protection

All portfolio materials are anonymized. No customer information, passwords, payment credentials, private order details or confidential administration data are included.
