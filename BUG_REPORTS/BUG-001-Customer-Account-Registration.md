# BUG-001 – Customer Account Registration Form Is Missing

## Summary

The **My Account** page displayed only the login form. New customers had no visible option to register an account.

The issue was reported by a real customer who attempted to access a previous account and could not find an alternative registration option.

---

## Business Impact

New customers could not create an account from the dedicated account page. This could increase support requests, reduce customer retention and create the impression that the website was malfunctioning.

Guest checkout remained available, so the main ordering flow was not completely blocked.

---

## Module

Customer Account / WooCommerce

---

## Environment

- Website: MR YU
- URL: `https://mryu.ro/my-account/`
- Platform: WordPress
- E-commerce plugin: WooCommerce
- Environment: Production
- Date identified: 2026-07-31

---

## Preconditions

- The visitor is not logged in.
- The visitor opens the **My Account** page.

---

## Steps to Reproduce

1. Open the MR YU website.
2. Navigate to the **My Account** page.
3. Observe the available forms.
4. Attempt to create a new customer account.

---

## Actual Result

Only the **Login** form was displayed.

There was no registration form and no visible option such as:

- Create an account
- Register
- New customer account

A visitor without valid login credentials could not create a new account from this page.

---

## Expected Result

The **My Account** page should display:

- a login form for existing customers;
- a registration form for new customers.

New customers should be able to enter their email address and receive an email containing a secure link for setting their password.

---

## Severity

**Major**

The issue blocked new customers from creating an account through the dedicated account page.

---

## Priority

**High**

The problem affected customer onboarding and could cause visitors to abandon the website or contact customer support.

---

## Root Cause

WooCommerce account creation options were disabled in:

`WooCommerce → Settings → Accounts & Privacy`

The following settings were not enabled:

- Allow customers to create an account during checkout.
- Allow customers to create an account on the My Account page.
- Allow customers to log into an existing account during checkout.

---

## Resolution

The following WooCommerce settings were enabled:

- Customer login during checkout.
- Customer registration during checkout.
- Customer registration on the My Account page.

The following existing options remained enabled:

- Automatic username generation.
- Password setup through an email link.
- Guest checkout.

---

## Retesting

The complete registration flow was retested.

### Registration form

- Login and registration forms were displayed side by side.
- A new email address was accepted.
- A new account was created successfully.

### Registration email

- The registration email was received successfully.
- The automatically generated username was included.
- The password setup link worked correctly.

### Password validation

The form rejected:

- an empty password;
- an insufficiently secure password;
- a password without an uppercase letter;
- a password without a numeric character;
- a password without a special character.

A secure password was accepted.

### Login and account access

After setting the password:

- login was successful;
- the customer dashboard loaded correctly;
- Orders was accessible;
- Addresses was accessible;
- Payment methods was accessible;
- Account details was accessible;
- Logout worked correctly.

---

## Additional Finding

The customer believed that the promotional voucher required an active customer account.

Testing confirmed that the voucher can also be used during guest checkout.

The customer only needs to open the coupon section during checkout and enter the promotional code.

Account registration is not required for applying a valid coupon.

---

## Status

**Fixed and retested**

---

## Evidence Available

- Before-fix screenshot showing only the login form.
- After-fix screenshot showing login and registration forms.
- Registration confirmation email.
- Customer dashboard screenshot.
- Manual password validation results.

---

## Regression Risk

Changes to WooCommerce account settings could affect:

- guest checkout;
- customer registration during checkout;
- login during checkout;
- registration emails;
- password setup;
- checkout layout.

These flows were checked after the configuration change.

---

## QA Conclusion

The issue was reproduced following a real customer report.

The cause was identified in the WooCommerce account configuration. The registration workflow was restored, tested end to end and confirmed operational.

---

## Interview Discussion

### Possible interview questions

**1. How did you reproduce this issue?**

I opened the **My Account** page as a logged-out user and observed that only the login form was displayed. There was no registration form or alternative option for a new customer to create an account.

**2. Why was the severity classified as Major instead of Critical?**

The issue blocked customer registration, which is an important feature, but customers could still place orders using guest checkout. The main ordering flow was therefore still available.

**3. How did you identify the root cause?**

I reviewed the WooCommerce account settings and found that customer registration was disabled for both the **My Account** page and checkout.

**4. How did you verify the fix?**

I created a new test account, confirmed that the registration email was received, opened the password setup link, created a valid password, logged in and checked the customer dashboard.

**5. What security-related checks did you perform?**

I verified that the password form rejected empty and weak passwords and required a stronger password containing uppercase characters, numbers and a special character.

**6. What regression areas did you check?**

I checked:

- guest checkout;
- registration on the My Account page;
- registration during checkout;
- login;
- registration email delivery;
- password setup;
- customer dashboard access.

**7. What business impact could this issue have caused?**

New customers could believe that the website was not working correctly, abandon the account creation process or contact customer support. It could also reduce customer retention because users could not access order history or saved details.

### Key lesson

Configuration changes in WooCommerce can completely disable an important customer workflow without requiring any code change. Account-related settings should therefore be included in regression testing after plugin updates or checkout changes.
