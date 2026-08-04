# MR YU – Project Timeline

This timeline summarizes the evolution of the MR YU production QA project. Detailed reproduction steps and evidence are stored in the linked defect reports, test sessions and checklists.

## 2026-06-25 – Initial production ordering assessment

The customer journey was reviewed from homepage and menu discovery through cart and checkout.

Primary investigation areas:

- delivery-address entry;
- cart and checkout separation;
- payment-method availability;
- mobile usability;
- customer patience and unnecessary friction;
- behavior when the initial address prompt is dismissed.

This assessment established the ordering flow as the highest-risk area of the project.

## 2026-06-28 – Responsive layout and navigation review

Homepage and menu behavior were reviewed across desktop and mobile layouts.

Focus areas included:

- hero-image presentation on mobile;
- headline sizing and line breaks;
- category navigation;
- home navigation from inner pages;
- visibility of menu, account and cart controls;
- persistent mobile controls.

Changes were validated iteratively to reduce the risk of breaking the live ordering experience.

## 2026-06-29 – Catalog and SEO data controls

A controlled WooCommerce/Rank Math workflow was prepared for the product catalog.

The work emphasized preservation of:

- existing product IDs;
- approved slugs;
- names and prices;
- category assignments;
- product images;
- Rank Math metadata;
- mobile-friendly product titles.

The export/import data later became the reference for avoiding accidental catalog overwrites.

## 2026-07-06 – Homepage performance investigation

A PageSpeed Insights review identified a performance risk affecting the homepage LCP image.

Confirmed observations:

- the LCP image was lazy-loaded;
- high fetch priority was not applied;
- the saved evidence reported a critical request-chain latency of approximately 1.449 seconds.

The finding remains documented as [PERF-001](PERFORMANCE/PERF-001-HOMEPAGE-LCP.md) and requires a current-state retest before implementation.

## 2026-07-20 – Menu taxonomy standardization

The online menu was reorganized into a clearer customer-facing structure covering:

1. Plită încinsă
2. Combo YU & Meniuri
3. Pui
4. Vită & porc
5. Rață, pește & fructe de mare
6. Noodles & spaghete
7. Orez & garnituri
8. Gustări & salate
9. Supe & ramen
10. Tofu & legume pe plită
11. Deserturi
12. Băuturi
13. Sosuri
14. Oferte & promoții

Terminology was standardized so **noodles/tăiței** and **spaghete din orez** remain distinct product types.

## 2026-07-27 to 2026-07-29 – Homepage and cart UX refinement

Homepage sections, product imagery and ordering calls to action were reviewed and refined.

Verified improvements documented for the cart experience included:

- live mini-cart subtotal updates;
- a direct “Modifică produsele din coș” action;
- calculation of the amount remaining to the 200 lei free-delivery threshold;
- a “Mai adaugă un preparat” call to action;
- correction of recommended-product image mismatches.

Homepage redesign work included hero, brand story, promotions and team content, with responsive checks treated as a release requirement.

## 2026-07-31 – Customer registration defect fixed

A real customer report revealed that the **My Account** page offered only login and no registration option.

Actions completed:

- reproduced the issue;
- identified disabled WooCommerce account settings;
- enabled registration on My Account and during checkout;
- kept guest checkout, automatic usernames and email password setup;
- verified registration email delivery;
- verified password validation, login and dashboard access;
- confirmed that BUNVENIT15 can be used without an account.

**Result:** Fixed and retested.

See [BUG-001](BUG_REPORTS/BUG-001-Customer-Account-Registration.md).

## 2026-07-31 – Cart quantity update defect documented

A cart defect requiring manual refresh after quantity changes was documented and its corrected behavior was retested.

Regression attention included:

- quantity increase and decrease;
- product removal;
- line totals and subtotal;
- coupon interaction;
- checkout transition;
- mini-cart synchronization.

**Result:** Fixed and retested.

See [BUG-002](BUG_REPORTS/BUG-002-Cart-Quantity-Update-Required-Refresh.md).

## 2026-08-01 – QA documentation standards added

The GitHub repository was repositioned as a production QA case study.

Added:

- structured defect documentation;
- severity and priority standards;
- confirmed-root-cause policy;
- interview discussion sections;
- initial changelog and timeline.

## 2026-08-04 – “Orez cu legume 300 g” published and verified

A missing standalone rice side dish was added to the WooCommerce catalog.

Verified:

- WooCommerce ID 2364;
- price 20 lei;
- intended category assignment;
- WebP product image;
- direct product URL;
- ingredients and weight;
- add-to-cart behavior;
- Rank Math score of 74/100 after publication.

**Result:** Published and verified.

See the [test-session report](TEST_SESSIONS/2026-08-04-PRODUCT-LISTING.md).

## 2026-08-04 – Repository completeness audit

The repository was compared with its own README and recent project work.

Gaps identified:

- no test plan;
- no reusable test-case suite;
- no regression checklist;
- incomplete timeline;
- missing performance record;
- missing catalog-validation session.

A complete documentation update was prepared on a separate branch to keep the default branch stable until review.
