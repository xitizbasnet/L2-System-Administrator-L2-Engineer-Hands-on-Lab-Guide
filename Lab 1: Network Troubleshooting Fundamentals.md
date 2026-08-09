# Lab 1: Network Troubleshooting Fundamentals

## 🎯 Objective

**Master network troubleshooting commands and understand network architecture basics.**

| **Lab Detail** | **Information**                                             |
| -------------- | ----------------------------------------------------------- |
| **Duration**   | 90 minutes                                                  |
| **Tools**      | `ipconfig`, `ping`, `tracert`, `netstat`, `nslookup`, `arp` |

---

## 🧭 Guided Task — Configure Network Interface & Check Connectivity

### Step 1 — Open an Administrative Command Shell

Open **Command Prompt (`cmd.exe`)** or **PowerShell** as **Administrator**.

### Step 2 — Display Network Configuration

Run the following command to view all network adapters, IP addresses, DNS servers, and DHCP status:

```cmd
ipconfig /all
```

### Step 3 — Identify the Active Network Adapter

Identify the **active network adapter** and note the **default gateway**.

### Step 4 — Test Internet Connectivity

Run the following command to test internet connectivity using four packets:

```cmd
ping 8.8.8.8
```

### Step 5 — Run a Continuous Ping

Run the following command to start a continuous ping:

```cmd
ping -t 8.8.8.8
```

Press **Ctrl+C** to stop the continuous ping.

### Step 6 — Analyze Ping Results

Analyze the output for:

* **Latency (ms)**
* **Packet loss**
* **TTL values**

---

## 🧪 Practice Task — Trace Route to Remote Host

### Step 1 — Trace the Network Path

Run the following command to trace the network path to a public DNS host:

```cmd
tracert google.com
```

### Step 2 — Document Each Hop

Document the following information for each hop:

* Hop number
* IP address
* Latency

### Step 3 — Limit the Number of Hops

Run the following command to limit the trace to **10 hops**:

```cmd
tracert -h 10 8.8.8.8
```

### Step 4 — Identify Slow or Timed-Out Hops

Identify any **slow or timeout hops**, which are marked with `*`.

### Step 5 — Investigate the Network Path

Investigate the path flow and identify potential bottlenecks.

---

## 🧩 Challenge Task — Network Diagnostics Deep Dive

### Step 1 — Display Active Connections and Listening Ports

Run the following command:

```cmd
netstat -an
```

This displays all active connections and listening ports.

### Step 2 — View the ARP Table

Run the following command:

```cmd
arp -a
```

Use the output to view the **ARP table** and identify MAC addresses on the local network.

### Step 3 — Refresh the DHCP Lease

Run the following commands in sequence:

```cmd
ipconfig /release
ipconfig /renew
```

This releases the current DHCP lease and requests a new lease.

### Step 4 — Verify the New Configuration

Monitor the change in IP address assignment and verify the new network configuration.

### Step 5 — Test DNS Resolution

Run the following command to test DNS resolution:

```cmd
nslookup microsoft.com
```

---

## 💡 3 BEST PRACTICE TIPS

> [!TIP]
> **Always document baseline network metrics** (latency, packet loss) when systems are healthy.

> [!TIP]
> **Use `ping -t` for continuous monitoring.** Press **Ctrl+C** to stop the command and review the statistics.

> [!TIP]
> **Tracert helps identify where latency occurs.** More than 15 hops is unusual for internal networks.

> [!TIP]
> **DNS resolution failures often precede connectivity issues.** Test `nslookup` early in troubleshooting.

> [!TIP]
> **Save network configurations** using the following command for reference:

```cmd
ipconfig /all > network_config.txt
```
