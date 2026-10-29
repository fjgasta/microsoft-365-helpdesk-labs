# INC0001005 — User Offboarding and Access Revocation

**Status:** Planned — not yet performed  
**Environment:** JGasta Labs Microsoft 365 / Microsoft Entra test tenant (non-production)  
**Ticket type:** Simulated IT service request / Identity and Access Management (IAM)

## Scenario

Human Resources notifies the IT help desk that a fictional employee is leaving the organization. IT must revoke access to Microsoft 365 while documenting each step and validating the result.

## Objectives

- Confirm the offboarding request and identify the correct fictional test user.
- Review the user's assigned licenses, roles, and authentication methods before making changes.
- Block future sign-ins and revoke active sessions where supported.
- Review group memberships and remove access as appropriate for the test scenario.
- Handle license removal and account retention or deletion only after confirming the intended scope.
- Verify the account can no longer access Microsoft 365 and document the outcome.

## Safety and Scope

Use **only a disposable fictional test account** created for this lab. Do not offboard the tenant administrator or an account needed for other portfolio exercises. **Do not delete any account or mailbox without first considering retention and recovery implications.** Revoking sessions, blocking sign-in, and removing licenses are different actions and should be tested separately. Do not upload passwords, access tokens, recovery codes, or other sensitive information.

## Planned Procedure

- [ ] Select a disposable fictional test user and document the starting state.
- [ ] Record the assigned Microsoft 365 license, account status, and relevant group memberships.
- [ ] Block sign-in for the user.
- [ ] Revoke existing sign-in sessions using available Microsoft Entra controls.
- [ ] Verify the access restrictions with a new sign-in attempt, without exposing credentials.
- [ ] Review any group memberships and license assignments; make changes only as appropriate for the scenario.
- [ ] Document account retention/deletion decision and leave deletion unperformed unless explicitly approved for the test.
- [ ] Capture sanitized screenshots and record the results.

## Verification Checklist

- [ ] Correct test account selected
- [ ] Block sign-in confirmed
- [ ] Existing sessions revoked where supported
- [ ] New sign-in blocked or documented with observed result
- [ ] Group/license actions documented accurately
- [ ] Final account state and ticket resolution documented

## Screenshot Evidence — Planned

Upload sanitized original screenshots to `screenshots/` after performing the lab. Suggested filenames:

1. `01-user-before-offboarding.jpg` — initial account overview
2. `02-account-access-review.jpg` — relevant license and role details
3. `03-block-sign-in.jpg` — sign-in block setting
4. `04-revoke-sessions.jpg` — session revocation confirmation
5. `05-access-verification.jpg` — non-sensitive verification result
6. `06-final-account-status.jpg` — final account state

These are **suggested** evidence names, not claims that the actions have already been completed.

## Skills to Demonstrate

Microsoft 365 administration, Microsoft Entra ID, IAM user lifecycle management, access revocation, session management, least privilege, license administration, security verification, and help desk ticket documentation.

## Result

**Not yet performed.** Update this section only after completing and verifying the hands-on steps.
