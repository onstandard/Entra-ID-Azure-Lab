# Entra ID Azure Lab

Azure-based Microsoft Entra ID lab covering cloud user and group management, bulk user creation, directory role assignment, multi-factor authentication, password reset, session management, and user lifecycle management.

---

## Table of Contents

1. [Entra ID Overview](#entra-id-overview)
2. [Creating Users](#creating-users)
3. [Bulk User Creation](#bulk-user-creation)
4. [Creating Groups and Adding Members](#creating-groups-and-adding-members)
5. [Assigning Directory Roles](#assigning-directory-roles)
6. [Multi-Factor Authentication](#multi-factor-authentication)
7. [Password Reset](#password-reset)
8. [Revoke User Sessions](#revoke-user-sessions)
9. [Delete and Restore a User](#delete-and-restore-a-user)

---

## Software Used

- Microsoft Azure
- Microsoft Entra ID

---

## Environments Used

- Microsoft Azure
- Windows Server 2022

---

## Entra ID Overview

Microsoft Entra ID is Microsoft's cloud-based identity and access management service used to manage users, groups, and access to resources.

- The architecture below illustrates how the Azure Virtual Machine, Microsoft Entra ID, Microsoft 365 Admin Center, and Active Directory Domain Services interact within this lab environment.

![Architecture Diagram](images/architecture-diagram.png)

---

## Creating Users

Cloud-only users were created directly in the Entra ID portal without the need for an on-premises Domain Controller.

- Cloud-only test users were created in Microsoft Entra ID to simulate managing identities in a modern cloud environment.

![Entra Users](images/entra-users.png)

---

## Bulk User Creation

Multiple users can be created at once in Entra ID using a CSV file upload, which is useful for onboarding large numbers of employees efficiently.

- Multiple users were created simultaneously using the bulk create feature in Microsoft Entra ID by uploading a formatted CSV file.

![Bulk Users](images/entra-bulk-users.png)

![Bulk Users](images/Total-Users-After-Bulk-Creation.png)

---

## Creating Groups and Adding Members

Security groups control access to resources and assign permissions. Microsoft 365 groups provide shared access to tools like Teams, SharePoint, and Outlook.

- A Security group and a Microsoft 365 group were created in Entra ID to demonstrate the difference between group types used for access control and collaboration.

![Entra Groups](images/entra-groups.png)

- Test users were added to the Cloud-IT-Staff security group to practice group membership management in Microsoft Entra ID.

![Entra Group Members](images/entra-group-members.png)

---

## Assigning Directory Roles

Directory roles define what administrative actions a user can perform within the tenant without giving them full Global Administrator access.

- The Helpdesk Administrator directory role was assigned to a test user in Entra ID, simulating how IT administrators grant elevated permissions to help desk staff.

![Directory Role](images/entra-role.png)

---

## Multi-Factor Authentication

MFA adds a second layer of verification beyond a password, reducing the risk of unauthorized account access.

- Multi-Factor Authentication was enabled for test users in Microsoft Entra ID to simulate enforcing MFA across an organization.

![MFA](images/entra-mfa.png)

---

## Password Reset

Administrators can reset a user's password directly from the Entra ID portal, generating a temporary password that the user must change on next login.

- A password reset was performed on a test user account from the Entra ID admin portal, simulating a common help desk request.

![Password Reset](images/entra-password-reset.png)

---

## Revoke User Sessions

Revoking a user's sessions immediately signs them out of all devices and applications. This is used when an account is compromised or an employee is terminated.

- A user's active sessions were revoked in Microsoft Entra ID to simulate an account security response.

![Revoke Sessions](images/entra-revoke-sessions.png)

---

## Delete and Restore a User

Deleted users in Entra ID are kept in a recycle bin for 30 days before being permanently removed. This allows administrators to restore accounts that were accidentally deleted.

- A test user account was deleted 
![Deleted User](images/entra-deleted-user.png)

- Then successfully restored from the Deleted users section in Microsoft Entra ID.

![Restore User](images/entra-restore-user.png)

---

## Challenges and Takeaways

**Challenges:**
- Bulk user creation requires a very specific CSV format and any formatting errors will cause the upload to fail
- Discovering that features like Self-Service Password Reset and Conditional Access require a premium Entra ID license, which are commonly used in real enterprise environments
- Understanding that revoking sessions does not disable the account, the user can still log back in unless the account is also disabled
- Revoking sessions and disabling an account are two separate actions and both may be needed during an offboarding or security incident

**Takeaways:**
- Learning that bulk user creation via CSV is a much more efficient approach than creating accounts one by one in large environments
- The 30 day deleted user retention period exists as a safety net and understanding when and how to use it prevents permanent data loss
- Getting comfortable switching between the Azure Portal and Entra ID admin center as separate but related tools
- Group membership in Entra ID directly impacts what resources and applications a user can access, making accurate group management critical
