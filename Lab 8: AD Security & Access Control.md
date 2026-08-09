# Lab 8: AD Security & Access Control

## 🎯 Objective

**Implement security best practices, manage NTFS permissions, and audit access in Active Directory.**

| **Lab Detail** | **Information**                                              |
| -------------- | ------------------------------------------------------------ |
| **Duration**   | 100 minutes                                                  |
| **Tools**      | NTFS Permissions, Audit Policy, `icacls`, Get-Acl PowerShell |

---

## 🧭 Guided Task — Configure NTFS Permissions

### Step 1 — Create a Shared Folder

Create a shared folder on a Windows server, for example:

```text
C:\SharedData
```

### Step 2 — Open Folder Security Properties

Right-click the folder and select:

**Properties → Security**

### Step 3 — Modify Permissions

Click **Edit** to modify the folder permissions.

### Step 4 — Add Security Groups

Add the required security groups:

**Edit → Add → type `domain\groupname`**

### Step 5 — Assign Permissions

Assign permissions based on the user's role:

* **Read (Read & Execute)**
* **Modify**
* **Full Control**

### Step 6 — Remove Unnecessary Groups

Remove unnecessary groups, such as:

* **Everyone**
* **Authenticated Users**

This helps improve security.

---

## 🧪 Practice Task — Enable & Configure Audit Logging

### Step 1 — Open Group Policy Management

On a **domain controller**, open **Group Policy Management (`gpmc.msc`)**.

### Step 2 — Edit the Default Domain Policy

Edit the **Default Domain Policy**.

### Step 3 — Navigate to Audit Policy

Navigate to:

**Computer Configuration → Policies → Windows Settings → Security Settings → Audit Policy**

### Step 4 — Enable Account and Logon Auditing

Enable the following policies for security tracking:

* **Audit account logon events**
* **Audit logon events**

### Step 5 — Apply Audit Settings

Run the following command on clients to apply the audit settings:

```cmd
gpupdate /force
```

### Step 6 — Review Security Events

Open **Event Viewer** and check the **Security** log for logon/logoff events.

---

## 🧩 Challenge Task — Advanced Permission Analysis & Troubleshooting

### Step 1 — View NTFS Permissions with PowerShell

Use PowerShell to view the permissions assigned to the shared folder:

```powershell
Get-Acl C:\SharedData | Select-Object -ExpandProperty Access
```

### Step 2 — Display NTFS Permissions with `icacls`

Use the following command to display NTFS permissions in command format:

```cmd
icacls C:\SharedData
```

### Step 3 — Troubleshoot Access Denied

Check the user's group memberships using:

```powershell
Get-ADUser username -Properties memberOf
```

### Step 4 — Verify Permission Inheritance

Verify permissions inheritance by checking the **parent folder permissions** for cascading rules.

### Step 5 — Check Effective Access

Enable effective permissions:

**Right-click folder → Security → Advanced → Effective Access tab**

### Step 6 — Verify Your Own AD Group Memberships

Run the following command to verify your own AD group memberships and effective permissions:

```cmd
whoami /groups
```

---

## 💡 3 BEST PRACTICE TIPS

> [!TIP]
> **Follow the principle of least privilege:** grant the minimum permissions required; users should have **Read** by default.

> [!TIP]
> **Remove inherited permissions from sensitive folders;** explicitly configure permissions instead of relying on defaults.

> [!TIP]
> **Test permissions before deploying to production:** create test groups and user accounts to validate access.

> [!TIP]
> **Enable auditing on shared folders with sensitive data;** review audit logs weekly for unauthorized access attempts.

> [!TIP]
> **Document all permission assignments with business justification;** maintain a permission matrix for compliance.
