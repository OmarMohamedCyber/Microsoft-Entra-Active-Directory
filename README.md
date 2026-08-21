# Microsoft Entra ID Administration Guide

This repository contains documentation for common Microsoft Entra ID administrative tasks including user management, group management, Multi-Factor Authentication (MFA), Microsoft Entra Connect synchronization, and access control concepts.

---

# Table of Contents

- Creating Users
- Deleting and Restoring Users
- Creating Groups
- Setting Up MFA
- Microsoft Entra Connect
- Synchronization Process
- RBAC vs ABAC
- Best Practices

---

# Creating Users

## Purpose

Create a new user account within Microsoft Entra ID and assign licenses, permissions, and group memberships.

## Procedure

### Step 1: Open Microsoft Entra Admin Center

Navigate to:

```text
https://entra.microsoft.com
```

### Step 2: Navigate to Users

```text
Identity
 └── Users
      └── All Users
```

### Step 3: Create User

Select:

```text
+ New User
```

Then select:

```text
Create New User
```

### Step 4: Enter User Information

Required fields:

```text
Display Name
First Name
Last Name
Username (UPN)
Password
```

Example:

```text
Display Name: John Smith
Username: jsmith@company.com
```

### Step 5: Assign Resources

Assign:

- Microsoft 365 License
- Security Groups
- Administrative Roles

### Step 6: Create

Click:

```text
Create
```

### Validation

Verify:

- User can sign in
- License has been assigned
- Group memberships are correct
- MFA registration is successful

---

# Deleting and Restoring Users

## Deleting a User

### Navigate To

```text
Identity
 └── Users
      └── All Users
```

### Delete User

1. Select the user.
2. Click:

```text
Delete User
```

3. Confirm deletion.

### Result

The account is moved to:

```text
Deleted Users
```

User accounts remain recoverable for up to 30 days.

---

## Restoring a User

### Navigate To

```text
Identity
 └── Users
      └── Deleted Users
```

### Restore

1. Select the deleted user.
2. Click:

```text
Restore User
```

### Verification

Verify:

- Group memberships
- License assignments
- Application access
- MFA settings

---

# Creating Groups

## Security Groups

### Purpose

Used for:

- Permission assignments
- Application access
- Azure role assignments
- Share permissions

### Create Security Group

Navigate to:

```text
Identity
 └── Groups
      └── All Groups
```

Select:

```text
New Group
```

Configure:

```text
Group Type: Security
Group Name: IT-Admins
Membership Type: Assigned
```

Add members and click:

```text
Create
```

---

## Microsoft 365 Groups

### Purpose

Provides:

- Shared mailbox
- Teams workspace
- SharePoint site
- Planner integration

### Create Group

Navigate to:

```text
Identity
 └── Groups
      └── New Group
```

Configure:

```text
Group Type: Microsoft 365
Group Name: Finance Team
```

Add members and owners.

Click:

```text
Create
```

---

# Setting Up Multi-Factor Authentication (MFA)

## Purpose

MFA adds another layer of security beyond passwords.

Supported authentication methods:

- Microsoft Authenticator
- FIDO2 Security Keys
- Passkeys
- Hardware Tokens

---

## Configure MFA Using Conditional Access

Navigate to:

```text
Protection
 └── Conditional Access
```

Select:

```text
New Policy
```

### Example Policy

Policy Name:

```text
Require MFA for All Users
```

### Assignments

Users:

```text
All Users
```

Cloud Apps:

```text
All Cloud Apps
```

### Grant Controls

Enable:

```text
Require Multi-Factor Authentication
```

### Enable Policy

Set:

```text
Enable Policy = On
```

Save the policy.

---

## User Registration

Users register MFA by visiting:

```text
https://aka.ms/mfasetup
```

Recommended methods:

1. Microsoft Authenticator
2. Passkeys
3. FIDO2 Security Keys

---

# Microsoft Entra Connect

## Overview

Microsoft Entra Connect synchronizes identities from on-premises Active Directory to Microsoft Entra ID.

Synchronized objects include:

- Users
- Groups
- Contacts
- Password Hashes

---

# Entra Connect Lab Setup

## Environment Example

### Domain Controller

```text
DC01.company.local
```

### Sync Server

```text
SYNC01.company.local
```

### Requirements

- Windows Server 2019 or later
- Domain Joined Server
- Enterprise Admin Account
- Microsoft 365 Global Administrator
- Internet Access

---
