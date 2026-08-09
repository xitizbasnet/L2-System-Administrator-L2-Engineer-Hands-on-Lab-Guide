# Lab 4: Windows Client OS Troubleshooting

## 🎯 Objective

**Diagnose and resolve common Windows client operating system issues, including startup, services, and driver problems.**

| **Lab Detail** | **Information**                                          |
| -------------- | -------------------------------------------------------- |
| **Duration**   | 100 minutes                                              |
| **Tools**      | Event Viewer, Device Manager, `Services.msc`, `msconfig` |

---

## 🧭 Guided Task — Analyze System Logs & Event Viewer

### Step 1 — Open Computer Management

Right-click **This PC** and select **Manage**, or open **Computer Management (`compmgmt.msc`)**.

### Step 2 — Navigate to System Logs

Navigate to:

**Event Viewer → Windows Logs → System**

### Step 3 — Review Recent Events

Look for **Error** and **Warning** events from the past **24 hours**.

### Step 4 — Review Event Details

Click an error event to view:

* Event ID
* Source
* Event details

### Step 5 — Research the Event ID

Search the event ID in the **Microsoft Knowledge Base** or the **internal ticketing system**.

### Step 6 — Review Application Logs

Check **Application** logs for software-related errors and failures.

---

## 🧪 Practice Task — Device Driver Management

### Step 1 — Open Device Manager

Press:

```text
Windows key + X
```

Then select **Device Manager**.

### Step 2 — Identify Driver Issues

Look for devices with **yellow warning signs**, which may indicate unknown drivers or conflicts.

### Step 3 — Update a Device Driver

Right-click a device and select:

**Update driver → Search automatically for drivers**

### Step 4 — Check Network Adapter Drivers

For network adapters specifically, check the:

* Driver version
* Driver date

### Step 5 — Review Driver Details

Right-click a device and select **Properties** to view driver details and status.

### Step 6 — Roll Back a Driver

If issues persist, roll back to a previous driver version using the **Driver** tab.

---

## 🧩 Challenge Task — Service Management & Startup Optimization

### Step 1 — Open Services

Open **Services (`services.msc`)** and review all running services.

### Step 2 — Identify Service Errors

Identify services in an **Error** or **Warning** state. Double-click a service to check its **Startup Type**.

### Step 3 — Review Startup Type

For a failing service, check the **Startup Type**:

* **Disabled**
* **Manual**
* **Automatic**

### Step 4 — Review Service Dependencies

Review service dependencies and ensure prerequisite services are running.

### Step 5 — Manage Startup Programs

Use **`msconfig` (System Configuration)** to safely disable startup programs.

### Step 6 — Test in Safe Mode

Boot into **Safe Mode** to test system stability.

Use **F8 on startup**, or access Safe Mode through **Startup Settings**.

---

## 💡 3 BEST PRACTICE TIPS

> [!TIP]
> **Always check Event Viewer FIRST when a system is unstable;** errors often point directly to the root cause.

> [!TIP]
> **Use Device Manager to check driver dates;** drivers older than 2 years may need updates.

> [!TIP]
> **Services set to Automatic but failing should be investigated immediately** as they're critical to OS functionality.

> [!TIP]
> **Create a System Restore point before making driver or service changes;** roll back if issues occur.

> [!TIP]
> **`msconfig` Service tab shows startup services;** compare with `Services.msc` to understand dependencies.
