<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="Nmap"/>
</p>

---

# 🔍 TCP Scans in Nmap

TCP scans are the most common type of Nmap scan. They work by attempting to complete a full or partial TCP handshake with the target machine, which reveals information about open ports and services.

---

<h3 align="center">Types of TCP Scans</h3>

### 1️⃣ TCP Connect Scan (`-sT`)

```
nmap -sT 192.168.1.1
```

🔹 Performs a full TCP handshake (SYN → SYN-ACK → ACK).

✅ Works without root privileges
❌ Easier for intrusion detection systems (IDS) to detect

---

2️⃣ TCP SYN Scan (-sS) — Stealth Scan

```
sudo nmap -sS 192.168.1.1
```

🔹 Sends only a SYN packet and analyzes the response.

✅ Faster and stealthier
✅ Requires root privileges (uses raw sockets)
❌ May not work well if a firewall drops SYNs

---

3️⃣ Scan Specific TCP Ports

```
nmap -p 21,22,80,443 192.168.1.1
```

🔹 Use -p to specify target ports. You can also use port ranges like -p 1-1000.

---

## 🔍 What Port States Mean

| State        | Meaning                                                                 |
|--------------|-------------------------------------------------------------------------|
| `open`       | A service is actively listening on this port                            |
| `closed`     | No service is listening, but the port is reachable                      |
| `filtered`   | Nmap cannot determine if the port is open due to packet filtering       |
| `unfiltered` | The port is accessible but its state (open/closed) can't be determined  |

---

🔐 Common Use Cases

Checking if a web server is reachable on port 80 or 443

Discovering SSH access on port 22

Testing firewall rules and exposed services

---

💬 Example

```
sudo nmap -sS -p 22,80,443 -v scanme.nmap.org
```

> This command performs a SYN scan on ports 22, 80, and 443 with verbose output.

---

## ⚙️ Nmap Scan Summary

| Option      | Scan Type                 | Requires Root | Stealthy | Notes                          |
|-------------|---------------------------|---------------|----------|-------------------------------|
| `-sS`       | SYN Scan (Stealth)        | ✅            | ✅       | Default for privileged users  |
| `-sT`       | TCP Connect Scan          | ❌            | ❌       | Used if not run as root       |
| `-sU`       | UDP Scan                  | ✅            | ❌       | Slower, used for UDP services |
| `-sV`       | Version Detection         | ❌            | ❌       | Identifies service versions   |
| `-O`        | OS Detection              | ✅            | ❌       | Guesses remote OS             |
| `-A`        | Aggressive Scan           | ✅            | ❌       | Enables OS + version + script |
| `-p`        | Port Selection            | ❌            | —        | Specify specific ports        |

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/1%20-%20Basic/3%20-%20Basic%20Commands.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/2%20-%20Scan%20Types/2%20-%20UDP%20Scan.md">Next Page</a>
</p>
