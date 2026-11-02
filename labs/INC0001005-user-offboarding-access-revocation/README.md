# INC0001005 — User Offboarding and Access Revocation

**Status:** Completed — screenshot upload pending  
**Lab date:** November 2, 2026  
**Environment:** JGasta Labs Microsoft 365 / Microsoft Entra test tenant (non-production)  
**Ticket type:** Simulated help desk service request / Identity and Access Management (IAM)  
**Test user:** Philip Stone (fictional employee)

## Ticket Scenario

Human Resources reports that a fictional employee, Philip Stone, is leaving the organization. As an IT support analyst, review the account, restrict Microsoft 365 access, revoke sign-in sessions, remove group membership, reclaim the license, and test the sign-in outcome. Retain the test account rather than permanently deleting it.

## Initial Account Review

- Account: `Philip.stone@GastaLabs.onmicrosoft.com`
- Microsoft 365 Business Premium license: **Assigned**
- License availability before change: **22 of 25 available**
- Administrator roles: **None**
- Group membership: **JGasta Labs** (Microsoft 365 group; assigned, cloud-managed)

## Procedure Performed

1. Created and selected the fictional **Philip Stone** account in **Microsoft 365 admin center → Users → Active users**. Reviewed the account and confirmed no administrator access.
2. Opened **Licenses and apps** and recorded the assigned **Microsoft 365 Business Premium** license.
3. Selected **Block sign-in** and saved the change. Microsoft displayed a confirmation that Philip was blocked from signing in and would be signed out of Microsoft services within 60 minutes. The account profile subsequently displayed **Sign-in blocked**.
4. Opened **Microsoft Entra admin center → Entra ID → Users → Philip Stone**, selected **Revoke sessions**, and confirmed. A success notification stated **Successfully revoked sign-in sessions for Philip Stone**.
5. Opened Philip's **Groups** section and reviewed his single membership in the **JGasta Labs** Microsoft 365 group.
6. Removed Philip's membership in that group. Microsoft displayed **Successfully removed group membership**, and the refreshed list stated **Not a member of any groups**.
7. Returned to **Microsoft 365 admin center → Users → Active users → Philip Stone → Licenses and apps**, unchecked **Microsoft 365 Business Premium**, and saved. The interface confirmed **Your changes have been saved** and displayed **Licenses (0)** and **Apps (0)**; available Business Premium licenses increased to **23 of 25**.
8. Attempted a new sign-in using Philip's fictional account. Microsoft displayed: **Your account has been locked. Contact your support person to unlock it, then try again.** Access was not obtained during the test.

## Verification Results

| Control | Observed result |
| --- | --- |
| Correct fictional user selected | Philip Stone |
| Account sign-in blocked | Confirmed in Microsoft 365 and Entra admin centers |
| Sign-in sessions revoked | Success notification confirmed |
| Group membership removed | No remaining group memberships displayed |
| Microsoft 365 Business Premium license removed | 0 assigned licenses; 23 of 25 available |
| Administrator roles | 0 |
| New sign-in test | Access not obtained; account-locked message shown |
| Account deletion | **Not performed** — test account retained |

**Interpretation:** The sign-in test showed an **account-locked** message. That alone does not establish the precise reason for the lock; the separately captured admin screens verify the disabled sign-in setting. Session revocation was confirmed by the administrative success notification, not by inspecting every client session.

## Screenshot Evidence — Awaiting Upload

The following eight screenshots were captured during the exercise. Upload the **original, reviewed/sanitized images** to the `screenshots/` directory with these filenames. Once uploaded, update this section with embedded image links.

| # | Filename | Evidence |
| --- | --- | --- |
| 1 | `01-user-before-offboarding.jpg` | Initial Philip Stone account |
| 2 | `02-license-before-removal.jpg` | Business Premium license assigned |
| 3 | `03-sign-in-blocked.jpg` | Block sign-in confirmation |
| 4 | `04-sessions-revoked.jpg` | Successful session revocation |
| 5 | `05-group-membership-before.jpg` | JGasta Labs membership |
| 6 | `06-group-membership-removed.jpg` | Membership removal confirmation |
| 7 | `07-license-removed.jpg` | License removal saved; 0 assigned |
| 8 | `08-sign-in-access-denied.jpg` | Observed account-locked message |

**Privacy note:** Review screenshots before publication. Remove any secrets, credentials, tokens, or unnecessary tenant identifiers. This lab used a fictional user in a test tenant.

## Skills Demonstrated

- Microsoft 365 Admin Center user administration
- Microsoft Entra ID user lifecycle and IAM operations
- Sign-in blocking and session revocation
- Microsoft 365 group membership management
- License reclamation and entitlement review
- Access verification, evidence collection, and help desk ticket documentation

## Ticket Resolution

**Completed:** Philip Stone's test account was blocked from sign-in, sign-in sessions were revoked, JGasta Labs group membership was removed, and the Business Premium license was reclaimed. A subsequent sign-in attempt did not obtain access and displayed an account-locked message. The user account was retained; no permanent deletion was performed.

**Documentation follow-up:** Upload and link the eight authentic lab screenshots.
