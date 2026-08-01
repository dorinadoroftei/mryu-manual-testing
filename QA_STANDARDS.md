# QA Standards

This document defines the documentation standards used throughout this QA portfolio.

---

# Bug Severity

## Critical

A defect that prevents customers from placing orders, completing payments or accessing essential functionality.

Examples:
- Checkout unavailable
- Payment failure
- Orders not created
- Data loss

---

## Major

A significant functional issue that affects an important feature but still has a workaround.

Examples:
- Customer registration unavailable
- Cart not updating correctly
- Search blocking navigation

---

## Medium

The feature works but with noticeable problems.

Examples:
- Incorrect validation
- Minor workflow interruption
- Partial functionality

---

## Minor

Visual or usability issues that do not prevent task completion.

Examples:
- Alignment problems
- Incorrect spacing
- Small responsive issues

---

## Enhancement

Suggested improvements that are not defects.

Examples:
- UX improvements
- Interface optimization
- Better customer guidance

---

# Priority

## Critical

Immediate production fix required.

## High

Should be fixed as soon as possible.

## Medium

Planned for an upcoming release.

## Low

May be addressed in a future improvement cycle.

---

# Bug Report Rules

Every Bug Report should contain:

- Summary
- Business Impact
- Module
- Environment
- Preconditions
- Steps to Reproduce
- Actual Result
- Expected Result
- Severity
- Priority
- Root Cause
- Resolution
- Retesting
- Regression Areas
- Evidence
- QA Notes

---

# Root Cause Policy

A root cause must only be documented when confirmed by available evidence.

If the technical cause is uncertain, use:

**Root Cause: Not confirmed**

QA documentation must distinguish verified facts from assumptions.

---

# Repository Goal

This repository documents manual QA activities performed on a live production WordPress and WooCommerce website.

The objective is to demonstrate real-world testing experience through structured documentation, reproducible defect reports and professional QA practices.
