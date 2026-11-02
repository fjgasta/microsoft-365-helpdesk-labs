# INC0001006 — Security Groups & Group-Based SharePoint Access

**Status:** Completed — November 2, 2026  
**Environment:** JGasta Labs Microsoft 365 test tenant (non-production)  
**Ticket type:** Simulated IT service request  
**Platforms:** Microsoft Entra admin center, SharePoint admin center, SharePoint Online

## Service Request

The fictional IT Support department needs a maintainable way to give authorized employees access to a private SharePoint team site without granting permissions separately to every user.

**Test user:** Alex Johnson  
**Entra security group:** `IT-Support-Team`  
**SharePoint site:** IT Support Lab  
**Site URL used for testing:** `https://gastalabs.sharepoint.com/sites/ITSupportLab2`

## Objectives

- Create a Microsoft Entra security group for the IT Support team.
- Add a fictional test user to the security group.
- Assign the security group to the SharePoint site's Members group.
- Verify access and ability to create a document as the test user.
- Distinguish resource permissions from Entra administrative directory roles.

## Procedure Performed

1. Opened **Microsoft Entra admin center > Groups > All groups > New group**.
2. Configured a **Security** group named `IT-Support-Team` with **Assigned** membership and description `Security group for IT Support team members`. Left **Microsoft Entra roles can be assigned to the group** disabled.
3. Created the group and verified it appeared in **All groups**.
4. Added **Alex Johnson** as a direct member and verified the membership in both the group member list and Alex's group memberships.
5. Checked Alex's **Assigned roles** page. After a transient retrieval error, the page displayed **No directory roles assigned**. Also checked the security group's **Roles and administrators** page, which showed no roles.
6. Opened **SharePoint admin center > Sites > Active sites**, and created a private **Team site** named **IT Support Lab** for the access-control test. The resulting site appeared in the active sites list.
7. Reviewed the site's SharePoint permission groups. **Owners** had Full Control, **Members** had Edit, and **Visitors** had Read.
8. Opened **IT Support Lab Members** in advanced SharePoint permissions, selected the existing Entra group `IT-Support-Team`, and shared access with that group.
9. Verified that `IT-Support-Team` appeared in the **IT Support Lab Members** group.
10. Signed in as **Alex Johnson** in a separate browser session and successfully loaded the private IT Support Lab site.
11. Opened **Documents** and created a Word document named `IAM-Access-Test.docx`. The library showed **Modified By: Alex Johnson**, confirming write access.

## Verification Results

| Check | Observed result |
| --- | --- |
| Entra security group created | Pass — `IT-Support-Team` appeared in All groups |
| Test user membership | Pass — Alex Johnson appeared as a member |
| Directory admin roles | No directory roles assigned to Alex; none shown for the security group |
| SharePoint group assignment | Pass — `IT-Support-Team` appeared in IT Support Lab Members |
| Site access | Pass — Alex opened the private site |
| Edit/write permission | Pass — Alex created `IAM-Access-Test.docx` |
| Revocation test | Not performed in this exercise |
| OneDrive permissions | Not tested in this exercise |

## Security Concepts

- **Group-based access management:** Assign a security group to a resource permission group, rather than adding individual users to the resource.
- **Least privilege:** Use the SharePoint Members group's Edit access for a contributor, instead of Owners' Full Control.
- **Permission inheritance through membership:** Alex's membership in `IT-Support-Team` allowed him to access the site and create a document.
- **Administrative roles vs. resource permissions:** Membership in an Entra security group does **not** automatically grant an Entra administrator role. This lab tested SharePoint resource access, not assignment of a directory administrative role.
- **Validation:** Confirm access by signing in as the test user and performing a permitted operation, not just inspecting configuration.

## Troubleshooting / Notes

- The Entra **Assigned roles** page initially returned a directory-role retrieval error. A subsequent view displayed **No directory roles assigned**.
- The SharePoint site's final URL used the suffix `ITSupportLab2`; verification used the actual site URL.
- The successful document creation verifies write access. No negative-access or post-removal revocation test was performed.

## Screenshot Evidence

All 12 screenshot files have been uploaded to the adjacent `screenshots/` folder. Select any filename below to view the corresponding evidence.

| Suggested filename | Evidence |
| --- | --- |
| [01-security-group-configuration.jpg](screenshots/01-security-group-configuration.jpg) | New security group configuration |
| [02-security-group-created.jpg](screenshots/02-security-group-created.jpg) | Group visible in Entra All groups |
| [03-group-membership.jpg](screenshots/03-group-membership.jpg) | Alex Johnson in IT-Support-Team |
| [04-user-group-memberships.jpg](screenshots/04-user-group-memberships.jpg) | Alex's group memberships |
| [05-no-directory-roles.jpg](screenshots/05-no-directory-roles.jpg) | No directory roles assigned |
| [06-sharepoint-site-created.jpg](screenshots/06-sharepoint-site-created.jpg) | IT Support Lab in Active sites |
| [07-sharepoint-permission-levels.jpg](screenshots/07-sharepoint-permission-levels.jpg) | Members Edit, Owners Full Control, Visitors Read |
| [08-security-group-selected.jpg](screenshots/08-security-group-selected.jpg) | IT-Support-Team selected for SharePoint sharing |
| [09-security-group-added.jpg](screenshots/09-security-group-added.jpg) | IT-Support-Team listed in SharePoint Members |
| [10-alex-signed-in.jpg](screenshots/10-alex-signed-in.jpg) | Alex Johnson signed in |
| [11-alex-sharepoint-access.jpg](screenshots/11-alex-sharepoint-access.jpg) | Private SharePoint site opened as Alex |
| [12-alex-document-created.jpg](screenshots/12-alex-document-created.jpg) | IAM-Access-Test.docx created by Alex |

**Evidence status:** All 12 image files were verified in this GitHub repository and linked above. Review screenshots for sensitive tenant/account details before publishing.

## Resolution

**Resolved.** Configured an Entra security group, assigned it to the SharePoint site's Members group, and verified that the test user could access the private site and create a document. The result demonstrates practical security-group administration, resource permission assignment, and end-to-end IAM access validation.

## Cleanup / Rollback (Optional, Not Performed)

After evidence collection, an administrator can remove `IT-Support-Team` from the SharePoint Members group, remove Alex from the Entra security group, and delete the test document/site if no longer needed. A revocation verification would be a useful follow-up exercise.
