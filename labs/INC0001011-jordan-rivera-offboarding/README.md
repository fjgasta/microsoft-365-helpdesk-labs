# Supplemental Practice — Employee Offboarding: Jordan Rivera

**Status:** Supplemental practice only — not counted as a separate numbered lab; screenshot publication pending  
**Environment:** JGasta Labs — Microsoft 365 / Microsoft Entra ID test tenant  
**Scenario:** Fictional employee departure; retain account while revoking access

## Ticket Scenario

IT receives a simulated request to offboard Jordan Rivera. Restrict sign-in, invalidate sessions, remove group membership and Microsoft 365 licensing, and verify that the account cannot sign in. Review OneDrive and Exchange Online status without deleting data.

## Procedure and Observed Results

1. **Account review:** Opened Jordan Rivera's profile in Microsoft 365 admin center. Initial account had no administrator access.
2. **Block sign-in:** Blocked the account. The admin center confirmed that Jordan Rivera was blocked and existing Microsoft services sessions would be signed out within 60 minutes.
3. **Revoke sessions:** In Microsoft Entra ID, selected **Revoke sessions**. A success notification confirmed sign-in sessions were revoked.
4. **Password reset:** An attempted reset in Entra reported insufficient permissions or a disabled account. Retried in Microsoft 365 admin center and received **Password has been reset** confirmation. No password is recorded in this document.
5. **Group access:** Reviewed membership in the **JGasta Labs** Microsoft 365 group and removed Jordan. The Entra portal confirmed successful removal and displayed **Not a member of any groups**.
6. **License removal:** Reviewed the active Microsoft 365 Business Premium assignment, then removed the license in Microsoft 365 admin center. The interface confirmed changes saved and showed **Licenses (0)**.
7. **Sign-in validation:** A subsequent Jordan sign-in attempt displayed **Your account has been locked. Contact your support person to unlock it, then try again.** Access was not obtained.
8. **OneDrive review:** Reviewed the user's OneDrive administration tab, including storage and retention settings. No deletion or file-transfer action was demonstrated.
9. **Mail review:** The Microsoft 365 admin center Mail tab displayed **This user doesn't have an Exchange Online license**. This does not by itself prove that mailbox data was deleted.

## Verification

| Check | Evidence |
| --- | --- |
| Sign-in blocked | Admin center confirmation and blocked account status |
| Sessions revoked | Entra success notification |
| Password reset | Microsoft 365 admin center success confirmation |
| Group membership removed | Entra success notification; no memberships listed |
| Business Premium license removed | Microsoft 365 admin center: Licenses (0) |
| New sign-in prevented | Account-locked error; access not obtained |
| Exchange Online entitlement | Mail tab shows no Exchange Online license |
| OneDrive | Administrative settings reviewed; no deletion confirmed |
| Account deleted | Not performed |

**Limitations:** The account-locked sign-in message does not independently identify the cause of the lock. Mailbox deletion, OneDrive data transfer, and long-term retention were not tested. Changes to sign-in sessions may take time to propagate.

## Screenshot Checklist

The following filenames are the intended names for **original screenshots** from this exercise. Image links will be added after the original image files are confirmed in this folder.

| Filename | Evidence |
| --- | --- |
| `01-jordan-account-overview.jpg` | Account before offboarding |
| `02-sign-in-blocked-confirmation.jpg` | Block sign-in saved |
| `03-sessions-revoked.jpg` | Revocation success |
| `04-entra-reset-permission-error.jpg` | Entra reset troubleshooting |
| `05-password-reset-success.jpg` | Reset success |
| `06-group-membership-before.jpg` | Original JGasta Labs membership |
| `07-group-membership-removed.jpg` | Successful removal |
| `08-license-before-removal.jpg` | Business Premium assigned |
| `09-license-removed.jpg` | Licenses (0) |
| `10-sign-in-denied.jpg` | Account locked at sign-in |
| `11-onedrive-review.jpg` | OneDrive administrative review |
| `12-mail-license-review.jpg` | Exchange Online license absent |
| `13-final-blocked-account-status.jpg` | Final blocked account view |

## Resolution

**Administrative offboarding steps completed.** Jordan Rivera's test account was blocked from sign-in, sessions were revoked, the password was reset, group membership was removed, and Microsoft 365 Business Premium licensing was reclaimed. A new sign-in attempt was unsuccessful. The account was retained for testing.

**Portfolio note:** Publish only authentic, reviewed screenshots. Never upload passwords, recovery codes, or access tokens.
