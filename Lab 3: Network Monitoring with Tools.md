# Lab 3: Network Monitoring with Tools

## 🎯 Objective

**Use packet analysis and network monitoring tools to identify performance and connectivity issues.**

| **Lab Detail** | **Information**                                             |
| -------------- | ----------------------------------------------------------- |
| **Duration**   | 90 minutes                                                  |
| **Tools**      | Wireshark, `netstat`, Performance Monitor, Resource Monitor |

---

## 🧭 Guided Task — Monitor Active Network Connections

### Step 1 — Open Task Manager

Open **Task Manager** by pressing:

```text
Ctrl+Shift+Esc
```

Navigate to the **Performance** tab.

### Step 2 — Monitor Network Usage

Click on the **Ethernet** or **Wi-Fi** adapter to view network usage in real time.

### Step 3 — Identify Network Activity

Navigate to the **Processes** tab and sort the processes by network activity.

### Step 4 — Identify High-Bandwidth Processes

Identify processes consuming high bandwidth and determine whether the network activity is expected.

### Step 5 — Open Resource Monitor

Switch to **Resource Monitor (`resmon.exe`)** for detailed network monitoring.

### Step 6 — Review Network Connections

Go to the **Network** tab and view:

* Active TCP connections
* Listening ports

---

## 🧪 Practice Task — Packet-Level Analysis with Wireshark

### Step 1 — Download and Install Wireshark

Download and install **Wireshark** from:

```text
wireshark.org
```

### Step 2 — Select the Network Interface

Launch Wireshark and select your active network interface.

### Step 3 — Start Packet Capture

Click the **shark fin** icon to start packet capture.

### Step 4 — Generate Network Traffic

Open a browser and visit a website while capturing traffic.

### Step 5 — Stop and Review the Capture

Stop the capture by clicking the **shark fin** icon and review the HTTP/HTTPS packets.

### Step 6 — Apply Packet Filters

Apply the following filters to isolate specific traffic types:

```text
http
dns
tcp.port==443
```

---

## 🧩 Challenge Task — Network Performance Analysis

### Step 1 — Open Performance Monitor

Open **Performance Monitor (`perfmon.exe`)** on Windows.

### Step 2 — Create a Data Collector Set

Create a custom **Data Collector Set** for network performance metrics.

### Step 3 — Add Performance Counters

Add the following counters:

* **Network Interface ® Bytes Received/Sent**
* **% Disk Time**

### Step 4 — Generate Network Traffic

Generate network traffic by performing activities such as:

* Downloading files
* Video streaming

Monitor the network activity in real time.

### Step 5 — Analyze Performance Logs

Stop the collector and analyze the generated logs for trends.

---

## 💡 3 BEST PRACTICE TIPS

> [!TIP]
> **Resource Monitor (`resmon.exe`) is faster than Wireshark for quick connection checks.**

> [!TIP]
> **Wireshark filters:** Use `ip.src==192.168.1.1` to filter by source IP and `tcp.port==80` for ports.

```text
ip.src==192.168.1.1
tcp.port==80
```

> [!TIP]
> **Performance Monitor** allows you to set alerts on thresholds; configure it for after-hours monitoring.

> [!TIP]
> **Save Wireshark captures (`.pcap` files) for forensics;** rotate logs monthly to save disk space.

> [!TIP]
> **Combine `netstat (-ano)` with Resource Monitor** to match process IDs to network connections.

```cmd
netstat -ano
```
