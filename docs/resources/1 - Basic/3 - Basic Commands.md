<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="Nmap"/>
</p>

---

# 🔧 Basic Nmap Commands

This section covers the most commonly used Nmap commands to help you get started with scanning hosts and networks.

> 💡 Tip: Run Nmap with `sudo` for more accurate results on some scans.

---

## 1️⃣ Scan a Single Host

```
nmap 192.168.1.1
```

Scans the default top 1000 TCP ports on the target IP.

---

2️⃣ Scan Multiple Targets

```
nmap 192.168.1.1 192.168.1.2
nmap 192.168.1.1,2,3
```

You can scan multiple hosts by separating them with spaces or commas.

---

3️⃣ Scan an Entire Subnet

```
nmap 192.168.1.0/24
```

Scans all 256 IPs in the subnet.

---

4️⃣ Scan Specific Ports

```
nmap -p 22,80,443 192.168.1.1
```

Scans only the specified ports.

---

5️⃣ Enable Verbose Output

```
nmap -v 192.168.1.1
```

Displays more details while scanning.

---

6️⃣ Do a Stealth SYN Scan (default)

```
sudo nmap -sS 192.168.1.1
```

Sends SYN packets to detect open ports without completing the TCP handshake.

---

7️⃣ Detect Operating System and Services

```
sudo nmap -A 192.168.1.1
```

Performs an aggressive scan: OS detection, version detection, script scanning, and traceroute.

---

8️⃣ Service Version Detection

```
nmap -sV 192.168.1.1
```

Tries to determine the version of services running on open ports.

---

9️⃣ Output Results to a File

```
nmap -oN results.txt 192.168.1.1
```

---

*️⃣ Other formats:

-oX for XML

-oG for grepable output

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/1%20-%20Basic/2%20-%20Installation.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/2%20-%20Scan%20Types/1%20-%20TCP%20Scan.md">Next Page</a>
</p>
