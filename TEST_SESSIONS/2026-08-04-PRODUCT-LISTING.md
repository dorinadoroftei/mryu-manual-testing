# Test Session – New Product Listing Validation

## Session information

- **Date:** 2026-08-04
- **Website:** https://mryu.ro
- **Environment:** Production
- **Area:** WooCommerce catalog
- **Change type:** New standalone product
- **Tester role:** Manual QA / catalog validation

## Objective

Verify that the newly published “Orez cu legume 300 g” product is correctly configured, visible and orderable without affecting the existing catalog.

## Product under test

| Field | Expected value |
|---|---|
| Product | Orez cu legume 300 g |
| WooCommerce ID | 2364 |
| Price | 20 lei |
| Category | Orez & Garnituri / Orez |
| Ingredients | Rice, carrot, peas, corn, egg and soy sauce |
| URL | https://mryu.ro/product/orez-cu-legume-300-g/ |
| Image | WebP, 1200 × 1200 px |
| Rank Math score after publication | 74/100 |

## Checks executed

| Check | Result |
|---|---|
| Direct product URL opens | Pass |
| Product name and 300 g weight display | Pass |
| Price displays as 20 lei | Pass |
| Ingredients display | Pass |
| Main image loads | Pass |
| Intended categories are assigned | Pass |
| Add-to-cart control is active | Pass |
| Product is available as a standalone menu item | Pass |

## Regression focus

The following connected risks were considered:

- unintended modification of existing product IDs;
- slug collision;
- incorrect category placement;
- replacement of validated WebP assets;
- broken add-to-cart behavior;
- inconsistent menu and product-page data;
- accidental changes to existing products during catalog work.

## Result

**Status: Passed – published and verified**

The product is available as a standalone item in the MR YU online menu.

## Follow-up

- Include the product in future representative catalog regression samples.
- Recheck the product after bulk imports or category restructuring.
- Preserve product ID 2364, the approved slug and validated media mapping unless a deliberate change is required.
