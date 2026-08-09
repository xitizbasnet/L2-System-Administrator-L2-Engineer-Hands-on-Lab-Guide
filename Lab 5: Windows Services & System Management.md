# Lab 5: Windows Services & System Management

## 🎯 Objective

**Master Windows service administration, registry configuration, and performance optimization using PowerShell.**

| **Lab Detail** | **Information**                                              |
| -------------- | ------------------------------------------------------------ |
| **Duration**   | 95 minutes                                                   |
| **Tools**      | PowerShell, Registry Editor, Task Scheduler, Disk Management |

---

## 🧭 Guided Task — PowerShell Service Management

### Step 1 — Open PowerShell as Administrator

Open **PowerShell** as **Administrator**:

**Right-click → Run as Administrator**

### Step 2 — List Running Services

Run the following command to list running services:

```powershell
Get-Service | Where-Object {$_.Status -eq 'Running'}
```

### Step 3 — Check Windows Update Service Status

Run the following command to check the status of the Windows Update service:

```powershell
Get-Service -Name wuauserv
```

### Step 4 — Start a Stopped Service

Run the following command to start a stopped service:

```powershell
Start-Service -Name wuauserv
```

### Step 5 — Stop a Running Service

Run the following command to stop a running service:

```powershell
Stop-Service -Name wuauserv
```

### Step 6 — Restart a Service

Run the following command to restart a service cleanly:

```powershell
Restart-Service -Name wuauserv
```

---

## 🧪 Practice Task — Registry Editing & Configuration

> [!WARNING]
> Registry modifications can affect Windows system functionality. Create a backup before making changes and document all modifications.

### Step 1 — Open Registry Editor

Open **Registry Editor (`regedit`)** from the Run dialog:

```text
Windows + R
```

### Step 2 — Navigate to the Windows Registry Key

Navigate to:

**HKEY_LOCAL_MACHINE → SOFTWARE → Microsoft → Windows**

### Step 3 — Create a Registry Backup

Create a backup using:

**File → Export → Save registry file with timestamp**

### Step 4 — Read Registry Properties with PowerShell

In PowerShell, run:

```powershell
Get-ItemProperty -Path 'HKLM:\Software\Microsoft\Windows\CurrentVersion'
```

### Step 5 — Modify a Registry Value

Modify a registry value using:

```powershell
Set-ItemProperty -Path 'HKLM:\...' -Name 'PropertyName' -Value 'NewValue'
```

### Step 6 — Document Registry Changes

Document all registry changes with **before/after screenshots**.

---

## 🧩 Challenge Task — Disk Management & Performance Tuning

### Step 1 — Open Disk Management

Run the following command to open the **Disk Management** console:

```cmd
diskmgmt.msc
```

### Step 2 — Review Disk Configuration

View all:

* Partitions
* Volumes
* Free space on local drives

### Step 3 — Check and Repair Disk Errors

Run the following command to check and repair disk errors:

```cmd
chkdsk C: /F
```

Schedule the operation for the **next restart** when prompted.

### Step 4 — Optimize Disk Fragmentation

Run the following command in PowerShell:

```powershell
defrag C: -U -V
```

### Step 5 — Review Scheduled Maintenance Tasks

Review **Task Scheduler** for maintenance tasks, including:

* Disk cleanup
* Backup
* Update checks

### Step 6 — Monitor Disk I/O

Monitor disk I/O using:

**Task Manager → Performance → Disk tab**

---

## 💡 3 BEST PRACTICE TIPS

> [!TIP]
> **Always export/backup the registry before making changes;** one mistake can require an OS reinstall.

> [!TIP]
> **Use `Get-Service` in PowerShell with filtering** for quick service status checks across many machines.

> [!TIP]
> **Service startup types:**
>
> * **Automatic** — Start with Windows.
> * **Manual** — Start by the user.
> * **Disabled** — Don't start.

> [!TIP]
> **Defragmentation on SSDs is unnecessary and reduces drive lifespan;** use only on traditional HDDs.

> [!TIP]
> **Schedule disk cleanup and defrag for off-hours** to minimize performance impact.
