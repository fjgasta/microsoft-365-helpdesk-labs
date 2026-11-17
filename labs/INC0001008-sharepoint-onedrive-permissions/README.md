# INC0001008 — SharePoint & OneDrive Permissions

**Status:** Completed — hands-on exercises documented with 12 uploaded screenshots  
**Environment:** JGasta Labs Microsoft 365 test tenant  
**Ticket type:** Simulated IT support / access-management request  
**Test user:** Alex Johnson  
**Services:** SharePoint Online, OneDrive for Business, Microsoft 365 admin center, Word for the web

## Service Request

Validate least-privilege access to shared documents. Give Alex Johnson view-only access where required, investigate overlapping SharePoint group permissions, and demonstrate how changing a OneDrive file's permissions affects editing capability.

## Work Performed

### Part A — SharePoint document permissions

1. Opened the **IT Support Lab** SharePoint site's Documents library and selected `IAM-Acces-Test.docx`.
2. Inspected **Manage access**, including **People**, **Groups**, and **Links**.
3. Shared the document directly with Alex Johnson using **Can view**.
4. Found an apparent mismatch: SharePoint's access summary initially displayed **Can edit**, while the detailed direct-access entry showed **Can view**.
5. Investigated site permissions, including the **IT Support Lab Members** group and the **IT-Support-Team** entry with **Edit** rights.
6. Confirmed Alex belonged to **IT-Support-Team** in Microsoft 365 admin center, then removed that group membership for troubleshooting.
7. Refreshed and rechecked document access. **Manage access** subsequently displayed **Alex Johnson — Can view**.
8. Tested the document in Alex's session; Word displayed **Viewing**.

**Troubleshooting lesson:** File-level view permission does not necessarily override editing access inherited through a site/group. Effective access must be tested, not inferred from a single sharing dialog.

### Part B — OneDrive file permissions

1. Signed in as the file owner and selected `Test_Test.docx` in **OneDrive → My files**.
2. Shared the file with Alex Johnson using **Can view**.
3. Verified the file appeared in Alex's **OneDrive → Shared → With you** list.
4. Opened the file as Alex and confirmed **Viewing** mode.
5. Returned to the owner's **Manage access** panel, reviewed **Direct Access**, and selected **Can edit** for Alex.
6. Opened the document again as Alex. The final screenshot shows **Editing** mode, visible document content, and a cloud save-status indicator.

## Verification Results

| Test | Observed result |
| --- | --- |
| SharePoint direct sharing | Alex was invited with **Can view** |
| SharePoint permission conflict | Group-based edit access investigated and membership adjusted |
| SharePoint final access display | **Can view** shown in Manage access |
| SharePoint user test | Document opened in **Viewing** mode |
| OneDrive view-only sharing | File appeared in Alex's Shared list and opened in **Viewing** mode |
| OneDrive permission change | **Can edit** selected for Alex |
| OneDrive final user test | Document opened as Alex in **Editing** mode with save-status indicator |

**Evidence limitation:** The final screenshot confirms editing mode and a saved document, but a separate owner-side comparison of a newly added test sentence was not captured. Do not describe that additional check as performed.

## Screenshot Evidence — Original Screenshots

The following 12 original screenshots have been uploaded to `screenshots/`. Select a filename to open the corresponding image:

| Filename | Evidence to capture from original screenshot |
| --- | --- |
| [`01-sharepoint-document-library.jpg`](screenshots/01-sharepoint-document-library.jpg) | IT Support Lab Documents library and test file |
| [`02-sharepoint-view-only-share.jpg`](screenshots/02-sharepoint-view-only-share.jpg) | Alex invited to view the SharePoint document |
| [`03-sharepoint-permission-conflict.jpg`](screenshots/03-sharepoint-permission-conflict.jpg) | Access summary showing edit versus direct view |
| [`04-sharepoint-site-groups.jpg`](screenshots/04-sharepoint-site-groups.jpg) | Site permissions showing group edit rights |
| [`05-alex-group-membership.jpg`](screenshots/05-alex-group-membership.jpg) | Microsoft 365 admin center showing IT-Support-Team membership |
| [`06-group-membership-removal.jpg`](screenshots/06-group-membership-removal.jpg) | Saved group membership change |
| [`07-sharepoint-final-can-view.jpg`](screenshots/07-sharepoint-final-can-view.jpg) | SharePoint Manage access showing Can view |
| [`08-onedrive-share-view.jpg`](screenshots/08-onedrive-share-view.jpg) | OneDrive share dialog / view-only invitation |
| [`09-alex-shared-with-you.jpg`](screenshots/09-alex-shared-with-you.jpg) | Alex's OneDrive Shared list |
| [`10-alex-onedrive-viewing.jpg`](screenshots/10-alex-onedrive-viewing.jpg) | OneDrive Word document in Viewing mode |
| [`11-onedrive-change-to-edit.jpg`](screenshots/11-onedrive-change-to-edit.jpg) | Owner's Manage access with Can edit selected |
| [`12-alex-onedrive-editing.jpg`](screenshots/12-alex-onedrive-editing.jpg) | Final Word screenshot as Alex in Editing mode |

Screenshot 10 should be checked against its label: the prepared ZIP noted that this image shows a view-only sharing confirmation rather than Word's Viewing mode. The lab's Viewing-mode test is separately described in the procedure.

## Resolution

**Lab exercise completed.** Demonstrated SharePoint access troubleshooting, effective-permission investigation, least-privilege file sharing, OneDrive view-to-edit changes, and user-side verification. All 12 screenshot files are uploaded and linked in this README.

## Skills Demonstrated

- SharePoint Online access management and group permissions
- Microsoft 365 group membership troubleshooting
- OneDrive for Business direct-access permissions
- Least-privilege sharing: **Can view** versus **Can edit**
- Separate-user verification and help desk documentation

*Fictional users and non-production test environment. Independent training project.*
