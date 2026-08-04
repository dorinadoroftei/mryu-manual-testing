# MR YU QA Documentation Standards

These standards keep the portfolio consistent, evidence-based and safe for public presentation.

## 1. Defect severity

| Severity | Definition | Examples |
|---|---|---|
| Critical | Prevents ordering, payment or another essential customer flow, with no reasonable workaround | Checkout unavailable, payment cannot start, orders not created, data loss |
| Major | Significantly affects an important feature, but a workaround or alternate path exists | Registration unavailable while guest checkout works, cart requires refresh |
| Medium | Feature remains usable but has a noticeable functional, validation or performance problem | Partial validation, degraded LCP, intermittent secondary behavior |
| Minor | Visual or usability issue that does not block task completion | Alignment, spacing, small responsive issue |
| Enhancement | Suggested improvement rather than a defect | Clearer guidance, fewer steps, improved layout |

Severity describes impact, not implementation effort.

## 2. Priority

| Priority | Meaning |
|---|---|
| Critical | Immediate production action required |
| High | Address as soon as possible because customer or revenue risk is significant |
| Medium | Plan for an upcoming controlled change |
| Low | Consider in a future improvement cycle |

Priority may change when business timing, frequency or available workaround changes.

## 3. Test result status

| Status | Meaning |
|---|---|
| Pass | Observed result matches the expected result |
| Fail | Observed result does not match the expected result |
| Blocked | Execution cannot continue because a dependency or environment is unavailable |
| Not Run | Scenario has not been executed |
| Not Applicable | Scenario does not apply to the change |

## 4. Defect lifecycle status

| Status | Meaning |
|---|---|
| Open | Reproduced and awaiting action |
| In progress | Investigation or correction is underway |
| Ready for retest | A proposed correction is available |
| Fixed and retested | Expected behavior was confirmed after the correction |
| Closed – not reproducible | Current evidence cannot reproduce the report |
| Deferred | Accepted for later action with the remaining risk recorded |

## 5. Required bug-report fields

Every report should contain:

- Summary
- Business impact
- Module
- Environment
- Preconditions
- Steps to reproduce
- Actual result
- Expected result
- Severity
- Priority
- Root cause or “Not confirmed”
- Resolution, when available
- Retesting
- Regression areas
- Status
- Evidence availability
- QA notes

## 6. Root-cause policy

A root cause is documented only when confirmed by available evidence.

When the technical cause is uncertain, use:

**Root Cause: Not confirmed**

The report may list confirmed observations, but it must not present a suspected plugin, theme, configuration or code path as fact.

## 7. Reproduction rules

- Use numbered, minimal steps.
- Start from a clear state.
- Record login, cart, schedule and cache preconditions.
- Avoid combining multiple defects in one report.
- Use exact visible labels where they improve reproducibility.
- Record whether the issue occurs on desktop, mobile or both.
- Confirm that the behavior is not an intended business rule before filing.

## 8. Retest and regression rules

A fix is not complete after the original step passes.

Retesting must also cover connected risks, for example:

- displayed and calculated cart values;
- cart, mini-cart and checkout synchronization;
- guest and account checkout;
- delivery and pickup;
- coupons and thresholds;
- desktop and mobile;
- login, registration email and password setup;
- unchanged catalog records after an import.

## 9. Evidence rules

Evidence may include:

- sanitized screenshots;
- short screen recordings;
- browser and device details;
- PageSpeed or DevTools output;
- anonymized test data;
- before/after observations.

Public evidence must not expose:

- customer names, addresses, email addresses or telephone numbers;
- passwords or authentication links;
- card, wallet or bank data;
- private order details;
- WordPress credentials or security tokens;
- confidential administration screens.

## 10. Production-testing policy

- Use low-risk actions.
- Do not finalize orders or payments without explicit business authorization.
- Do not perform load, stress or destructive testing.
- Use test accounts and anonymized data.
- Keep a rollback or backup path for high-risk changes.
- Avoid blind plugin, theme or page-builder updates.
- Preserve approved IDs, slugs and media mappings during catalog work.

## 11. Repository goal

This repository demonstrates real-world manual QA work on a live WordPress and WooCommerce system through structured test design, reproducible defect reports, controlled retesting and transparent documentation of remaining risk.
