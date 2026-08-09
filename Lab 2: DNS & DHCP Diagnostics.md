# Lab 2: DNS & DHCP Diagnostics

## 🎯 Objective

**Troubleshoot DNS resolution failures and DHCP lease issues in enterprise environments.**

| **Lab Detail** | **Information**                           |
| -------------- | ----------------------------------------- |
| **Duration**   | 75 minutes                                |
| **Tools**      | `nslookup`, `ipconfig`, `dcdiag`, `netsh` |

---

## 🧭 Guided Task — Diagnose DNS Resolution Issues

### Step 1 — Open Command Prompt

Open **Command Prompt** as **Administrator**.

### Step 2 — Identify DNS Servers

Run the following command and note the DNS servers currently in use:

```cmd
ipconfig /all
```

### Step 3 — Test DNS Resolution

Run the following command to test DNS resolution:

```cmd
nslookup example.com
```

### Step 4 — Query a Specific DNS Server

Run the following command to query a specific DNS server:

```cmd
nslookup example.com 8.8.8.8
```

### Step 5 — Compare DNS Results

Compare the results between the **default DNS server** and the **alternate DNS server**.

### Step 6 — Query an A Record

If resolution fails, run the following command to query the **A record** for the domain:

```cmd
nslookup -type=A example.com
```

---

## 🧪 Practice Task — Clear DNS Cache & Test Resolution

### Step 1 — View Cached DNS Entries

Run the following command to view cached DNS entries:

```cmd
ipconfig /displaydns
```

### Step 2 — Clear the DNS Resolver Cache

Run the following command to clear the DNS resolver cache:

```cmd
ipconfig /flushdns
```

### Step 3 — Verify DNS Resolution

Run the following command to verify that the cache was cleared:

```cmd
nslookup contoso.com
```

### Step 4 — Query Mail Exchange Records

Run the following command to query **mail exchange (MX) records**:

```cmd
nslookup -type=MX example.com
```

### Step 5 — Document DNS Query Differences

Document the differences between **cached** and **fresh DNS queries**.

---

## 🧩 Challenge Task — Advanced DHCP & DNS Troubleshooting

### Step 1 — Release the Current DHCP Lease

Run the following command to release the current DHCP lease:

```cmd
ipconfig /release
```

### Step 2 — Request a New DHCP Lease

Run the following command to request a new DHCP lease from the server:

```cmd
ipconfig /renew
```

### Step 3 — Verify the New Network Configuration

Monitor the process and verify the following:

* New IP address
* Subnet mask
* Gateway
* DNS servers

### Step 4 — Display Detailed IPv4 Configuration

Run the following command to view detailed IPv4 configuration:

```cmd
netsh interface ipv4 show config
```

### Step 5 — Perform a Detailed DNS Query

Run the following command to view detailed DNS query steps:

```cmd
nslookup -debug example.com
```

---

## 💡 3 BEST PRACTICE TIPS

> [!TIP]
> **Always test with multiple DNS servers** to isolate whether the issue is server-specific.

> [!TIP]
> **DNS cache (`ipconfig /displaydns`) can mask recurring DNS issues;** flush it regularly during troubleshooting.

> [!TIP]
> **Use `nslookup -type=` to query specific record types**, including `A`, `AAAA`, `MX`, `SRV`, and `NS`.

> [!TIP]
> **DHCP issues often cascade to DNS failures;** always release and renew after network changes.

> [!TIP]
> **Keep a list of reliable public DNS servers** (`8.8.8.8`, `1.1.1.1`) for backup testing.
