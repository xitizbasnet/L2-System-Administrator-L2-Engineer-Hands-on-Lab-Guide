# Lab 7: Active Directory User & Computer Management

## 🎯 Objective

**Manage user accounts, computers, and organizational units in Active Directory to maintain directory integrity.**

| **Lab Detail** | **Information**                                             |
| -------------- | ----------------------------------------------------------- |
| **Duration**   | 90 minutes                                                  |
| **Tools**      | Active Directory Users and Computers, `dsadd`, `Get-ADUser` |

---

## 🧭 Guided Task — Create & Manage User Accounts

### Step 1 — Open Active Directory Users and Computers

Open **Active Directory Users and Computers (`dsa.msc`)** on a domain controller.

### Step 2 — Navigate to the User Location

Navigate to the **Users** container or an **Organizational Unit (OU)**.

### Step 3 — Create a New User

Right-click and select:

**New → User**

Create a new user account.

### Step 4 — Enter User Information

Enter the following information:

* First name
* Last name
* Logon name (`samAccountName`)
* Password

### Step 5 — Configure Password Options

Configure the password options:

**User must change password at next logon**

This option helps enforce security.

### Step 6 — Verify the Account

Finish the user creation process and verify the account in the **Users** container.

---

## 🧪 Practice Task — Manage Group Membership

### Step 1 — Open User Properties

Double-click a user account to open its **Properties**.

### Step 2 — Review Group Memberships

Navigate to the **Member Of** tab to view group memberships.

### Step 3 — Add the User to Security Groups

Click **Add** to add the user to security groups, such as:

* **Domain Users**
* **Accounts Department**

### Step 4 — Verify the Group Name

Type the group name and click **Check Names** to verify it.

### Step 5 — Remove Unnecessary Groups

Remove the user from unnecessary groups:

1. Select the group.
2. Click **Remove**.

### Step 6 — Verify NTFS Permissions

Apply the changes and verify that **NTFS permissions** align with the new group memberships.

---

## 🧩 Challenge Task — Computer Management & Organizational Units

### Step 1 — Navigate to the Computers Container

In **Active Directory Users and Computers**, navigate to the **Computers** container.

### Step 2 — Review Domain-Joined Computers

View all domain-joined computers and their **last logon times**.

### Step 3 — Create an OU Structure

Create a new OU structure:

**Right-click domain → New → Organizational Unit**

### Step 4 — Create Department and Location OUs

Create OUs for departments, for example:

* **Finance**
* **IT**
* **HR**

Create OUs for locations, for example:

* **Mumbai**
* **Delhi**

### Step 5 — Move Computers to Appropriate OUs

Move computers to the appropriate OUs based on **location/department**.

### Step 6 — Maintain Computer Account Hygiene

Disable or delete inactive computer accounts that have **not logged in for 90+ days** to maintain directory hygiene.

---

## 💡 3 BEST PRACTICE TIPS

> [!TIP]
> **Use descriptive naming conventions for user accounts:** `FirstName.LastName` or `First.Last` (for example, `vinod.muleva`).

> [!TIP]
> **Enforce strong password policy through Domain Password Policy GPO;** never share user passwords via email.

> [!TIP]
> **Create security groups for role-based access control (RBAC);** assign permissions to groups, not individual users.

> [!TIP]
> **Disable accounts instead of deleting them;** retention allows recovery within the tombstone lifetime (**180 days default**).

> [!TIP]
> **Use PowerShell for bulk user/group operations:** `Get-ADUser`, `Set-ADUser`, and `Add-ADGroupMember` can improve efficiency.
