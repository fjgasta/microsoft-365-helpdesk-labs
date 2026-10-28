# INC0001002 — New Employee Onboarding

**Status:** Completed — account creation and configuration verified  
**Environment:** JGasta Labs, Microsoft 365 test tenant (not production)  
**Ticket type:** Simulated IT service request  
**Completion date:** October 28, 2026

## Scenario

HR requests a Microsoft 365 account for a fictional new hire, **Jordan Rivera**, joining the Human Resources department as an **HR Coordinator**.

## Objective

Provision a standard employee account, assign the required Microsoft 365 license, populate organizational profile attributes, and verify the saved configuration.

## New Hire Details

| Attribute | Value |
| --- | --- |
| Employee | Jordan Rivera (fictional) |
| Username | `jordan.rivera@GastaLabs.onmicrosoft.com` |
| Job title | HR Coordinator |
| Department | Human Resources |
| Office | Main Office |
| Access role | Standard user; no administrator access |
| License | Microsoft 365 Business Premium |
| Usage location | United States |

## Procedure Performed

1. Opened **Microsoft 365 Admin Center → Users → Active users → Add a user**.
2. Entered the fictional employee's name and username.
3. Enabled automatic temporary-password generation and required a password change at first sign-in in the creation wizard.
4. Set the usage location to **United States** and selected **Microsoft 365 Business Premium**.
5. Kept the role as **User (no administration access)**, following least-privilege principles.
6. Entered **HR Coordinator** as the job title, **Human Resources** as the department, and **Main Office** as the office.
7. Reviewed the configuration and selected **Finish adding**.
8. Received confirmation that **Jordan Rivera was added to active users**.
9. Reopened the user account and checked the account role, license, and contact information.

## Verification Checklist

- [x] Microsoft 365 confirmed the account was added to Active users
- [x] Name and account profile displayed correctly
- [x] User had no administrator access
- [x] Microsoft 365 Business Premium remained assigned after account creation
- [x] Job title saved as **HR Coordinator**
- [x] Department saved as **Human Resources**
- [x] Office saved as **Main Office**
- [ ] First sign-in and forced password change independently tested
- [ ] MFA registration tested (separate planned lab INC0001004)

The license verification screen showed **23 of 25 licenses available** after provisioning the account. The Business Premium trial indicated an expiration date of **November 27, 2026**.

## Screenshot Evidence

The following six screenshots were captured from the Microsoft 365 Admin Center during the onboarding lab and uploaded to this repository:

| Step | Screenshot |
| --- | --- |
| New user basics | [01 — New User Creation](screenshots/01-new-user-creation.jpg) |
| HR role and profile settings | [02 — Employee Profile Settings](screenshots/02-employee-profile-settings.jpg) |
| Final settings review | [03 — Onboarding Review](screenshots/03-onboarding-review.jpg) |
| Account creation confirmation | [04 — User Created Successfully](screenshots/04-user-created-successfully.jpg) |
| Post-creation license check | [05 — License Verification](screenshots/05-license-verification.jpg) |
| Saved contact information | [06 — Employee Profile Verified](screenshots/06-employee-profile-verified.jpg) |

**Evidence upload:** Completed. Screenshots show the lab configuration and verification; they do not establish that first sign-in or MFA enrollment was tested.

**Security note:** Screenshots should not expose temporary passwords, authentication codes, payment details, or tenant secrets.

## Skills Demonstrated

Microsoft 365 Admin Center; new-hire onboarding; user provisioning; software license assignment; organizational attribute management; least-privilege access; post-creation verification; service-request documentation.

## Result

**Resolved for lab scope:** Jordan Rivera's fictional employee account was created, licensed, and its organizational profile settings verified. Interactive sign-in and MFA enrollment were not tested as part of this exercise.
