# Lab 6: Group Policy Administration

## 🎯 Objective

**Manage Group Policy Objects (GPOs) to enforce security and configuration standards across Windows domains.**

| **Lab Detail** | **Information**                                   |
| -------------- | ------------------------------------------------- |
| **Duration**   | 85 minutes                                        |
| **Tools**      | Group Policy Management, `gpedit.msc`, `gpresult` |

---

## 🧭 Guided Task — Edit Local Group Policy

### Step 1 — Open Group Policy Editor

Open **Group Policy Editor (`gpedit.msc`)** on a domain-joined machine.

### Step 2 — Navigate to System Policies

Navigate to:

**Computer Configuration → Administrative Templates → System**

### Step 3 — Locate a Policy

Locate a policy such as:

**Specify intranet Microsoft Update service location**

### Step 4 — Open Policy Properties

Double-click the policy to open its properties.

### Step 5 — Configure the Policy

Set the policy to **Enabled** and configure the intranet update service URL.

### Step 6 — Refresh Group Policy

Apply the policy and run the following command to refresh Group Policy immediately:

```cmd
gpupdate /force
```

---

## 🧪 Practice Task — Apply Domain-Level Group Policies

### Step 1 — Open Group Policy Management

On a **domain controller**, open **Group Policy Management (`gpmc.msc`)**.

### Step 2 — Review the Domain

Expand the domain node and view the **default Domain Controllers policy**.

### Step 3 — Create a New GPO

Create a new GPO:

**Right-click the domain → Create a GPO in this domain → OK**

### Step 4 — Name and Link the GPO

Name the GPO, for example:

**`L2-Security-Standards`**

Then link it to an **organizational unit (OU)**.

### Step 5 — Configure the GPO

Right-click the GPO and select **Edit** to configure its settings.

### Step 6 — Apply Password Policy

Navigate to:

**Computer Configuration → Policies → Windows Settings → Security Settings → Account Policies**

Apply the required password policy settings.

---

## 🧩 Challenge Task — GPO Reporting & Troubleshooting

### Step 1 — Generate a Group Policy Results Report

On a client machine, run:

```cmd
gpresult /h gpresult.html
```

This generates a Group Policy results report.

### Step 2 — Review the HTML Report

Open the HTML report in a browser and review:

* Applied GPOs
* Denied GPOs

### Step 3 — Generate a User-Specific Report

Run the following command for user-specific policies:

```cmd
gpresult /scope:user /h user_gpresult.html
```

### Step 4 — Check for Policy Conflicts

Check for:

* Policy application errors
* Conflicting policies

### Step 5 — Check GPO Replication

On the domain controller, run:

```cmd
gpotool.exe
```

Use the tool to check **GPO replication status**.

### Step 6 — Document Applied Policies

Document applied policies, including:

* **Source**
* **Scope** — User/Computer
* **Enforcement status**

---

## 💡 3 BEST PRACTICE TIPS

> [!TIP]
> **Always test GPOs on pilot OUs** before applying them to production organizational units.

> [!TIP]
> **Run `gpupdate /force` after GPO changes.** User policies require logoff/login, while computer policies require a restart.

> [!TIP]
> **Use `gpresult` reports** to verify GPO application and troubleshoot policy failures.

> [!TIP]
> **GPO processing order:** Local GPO → Site → Domain → Organizational Unit (**LSDO**).

> [!TIP]
> **Document all GPO changes with change tickets**, including the policy name, purpose, and affected OUs.
