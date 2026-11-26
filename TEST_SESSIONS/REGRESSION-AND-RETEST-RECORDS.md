# Regression and retest records

Use this page to link a release or fix to the checks actually executed. The reusable scenarios live in [Core Test Cases](../TEST_CASES/CORE-FLOWS.md) and the [Regression Checklist](../CHECKLISTS/REGRESSION-CHECKLIST.md).

## Historical cart retest

| Period recorded | Defect and case | Recorded observation |
|---|---|---|
| July 2026 (resolution month in the defect report) | [BUG-002](../BUG_REPORTS/BUG-002-Cart-Quantity-Update-Required-Refresh.md#retesting) · [TC-003](../TEST_CASES/CORE-FLOWS.md#tc-003--add-product-and-synchronize-cart-state) | The existing report documents quantity updates without manual refresh and continuation to checkout. The exact retest date, browser version, device and numeric observations are unavailable in the source. |

## Future defect retest

Record the execution date, environment, browser and version, and device at the top of each run. Use approved evidence references. Omit customer identifiers, credentials, email content and payment information.

| Defect and case | Check | Expected | Actual | Outcome | Approved evidence |
|---|---|---|---|---|---|
| BUG-002 · TC-003 | Cart after changing quantity without refresh | Item count and subtotal match the new quantity | — | Pending | — |
| BUG-002 · TC-003 | Continue to checkout | Checkout reflects the updated cart | — | Pending | — |
| BUG-001 · TC-007 | Form, registration email, password validation and login | Record one observation for each step | — | Pending | — |
| BUG-001 · TC-007 | Follow-up finding | Record its current status and disposition | — | Pending | — |

## Future release run

Record the date, release or change reference, environment and browser/device before executing this plan. Suggested P0 cases cover checkout completion and payment presentation. Suggested P1 cases cover cart, promotions, account and navigation. Adjust priorities to the release impact.

| Priority | Scope and cases | Expected | Actual | Outcome | Evidence or reason |
|---|---|---|---|---|---|
| P0 | [TC-004 and TC-005](../TEST_CASES/CORE-FLOWS.md#tc-004--validate-delivery-checkout) · Delivery and pickup checkout | Selected mode and totals are consistent through order review | — | Pending | — |
| P0 | [TC-009](../TEST_CASES/CORE-FLOWS.md#tc-009--validate-payment-method-presentation) · Payment presentation | Intended methods are visible and clearly labeled | — | Pending | — |
| P1 | [TC-003](../TEST_CASES/CORE-FLOWS.md#tc-003--add-product-and-synchronize-cart-state) · Cart | Count and totals update correctly | — | Pending | — |
| P1 | [TC-006](../TEST_CASES/CORE-FLOWS.md#tc-006--apply-a-promotional-code-during-guest-checkout) · Promotions | Eligible discounts are reflected in totals | — | Pending | — |
| P1 | [TC-007](../TEST_CASES/CORE-FLOWS.md#tc-007--register-a-customer-account) · Account | An approved test account can register and sign in | — | Pending | — |
| P1 | [TC-011](../TEST_CASES/CORE-FLOWS.md#tc-011--validate-mobile-navigation-and-persistent-controls) · Mobile navigation | Intended controls remain reachable and usable | — | Pending | — |

Use Pass, Fail, Blocked or N/A after review. Record the reason for blocked, inapplicable or unexecuted cases. Complete real orders or payment steps only when the run scope explicitly authorizes them.
