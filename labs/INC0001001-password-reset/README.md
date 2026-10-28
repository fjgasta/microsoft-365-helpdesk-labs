# INC0001001 — Microsoft 365 Password Reset

**Status:** Completed — password reset and test-user sign-in verified  
**Environment:** Microsoft 365 test tenant (non-production)  
**Ticket category:** Identity and access / Help Desk  
**Date:** October 27, 2026

## Scenario

A fictional employee, **Alex Johnson**, needs help regaining access to a Microsoft 365 work account. As the administrator, I created a test account, performed a password reset, required a password change at the next sign-in, and verified that the account could authenticate.

## Tools and skills

- Microsoft 365 Admin Center — user management and password reset
- Microsoft Entra work-account sign-in
- Password lifecycle and forced password change
- MFA enrollment flow and basic troubleshooting
- Ticket documentation and evidence collection

## Procedure and verification

1. **Created the test user.** Added Alex Johnson in Microsoft 365 Admin Center. The account had **no product license** assigned.
2. **Located the account.** Found and selected Alex Johnson under **Users → Active users**.
3. **Configured the reset.** Enabled **Automatically create a password** and **Require this user to change their password when they first sign in**.
4. **Reset the password.** Microsoft displayed a successful password-reset confirmation. Temporary credentials were kept out of the repository.
5. **Tested sign-in.** Used the work/school sign-in page at `login.microsoftonline.com`, not the personal-account page at `login.live.com`.
6. **Verified the forced change.** Microsoft displayed the **Update your password** form. After the change, the test user advanced into security registration.
7. **Troubleshot an interruption.** An initial **Keep your account secure** attempt showed `BadRequest`. A subsequent sign-in progressed to the Microsoft Authenticator setup flow.
8. **Verified authentication.** The test user reached Microsoft 365 with **Alex** displayed in the account interface.

## Evidence

Screenshots are in the [screenshots folder](screenshots/). The evidence sequence covers:

| Step | Evidence | Result |
|---|---|---|
| 01 | Test user creation | User added |
| 02 | Password-reset options | Forced password change selected |
| 03 | Reset confirmation | Reset succeeded |
| 04 | Update your password prompt | Password change required |
| 05 | Microsoft 365 after sign-in | Test account authenticated; app list failed to load |

**Security note:** Do not commit temporary passwords, MFA QR codes, verification codes, or recovery secrets. Screenshots should be redacted before publishing. Any recreated or enhanced screenshots should be labeled as illustrations rather than original system evidence.

## Troubleshooting notes

- **Personal vs. work account:** `login.live.com` did not recognize the test work account. Switching to `login.microsoftonline.com` resolved that sign-in path issue.
- **Security registration:** The initial `BadRequest` on the security setup page was followed by a successful return to the authentication flow. The exact root cause was not established.
- **Application access:** After sign-in, Microsoft 365 displayed **“Sorry, we ran into a problem loading this list.”** This is a separate application-loading issue. The account was unlicensed; the cause of the loading error was not confirmed.

## Outcome

**Password reset workflow: Completed.** Successfully created a fictional account, performed an administrator password reset, enforced a password change, and observed an authenticated Microsoft 365 session.

**Follow-up:** Investigate the Microsoft 365 app-list loading error separately if app access becomes part of another lab. Do not interpret that error as proof that authentication failed.

## Lessons learned

Help Desk verification should cover more than the reset confirmation: test the new credentials, confirm the required password change, distinguish authentication from application authorization, and record unresolved issues without guessing at their causes.
