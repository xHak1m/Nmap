<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 🌐 UDP Scanning with Nmap

UDP (User Datagram Protocol) scans are essential for discovering non-TCP services like DNS, SNMP, NTP, and more. Unlike TCP, UDP is connectionless, which makes detection trickier and slower — but just as important.

---

## 🚀 Basic UDP Scan

```
sudo nmap -sU 192.168.1.1
```

Scans the top 1000 UDP ports.

Requires sudo to send raw packets.

Slower than TCP scans and prone to timeouts.

---

🎯 Scan Specific UDP Ports

```
sudo nmap -sU -p 53,161 192.168.1.1
```

-p 53,161: Only scans DNS and SNMP ports.

Useful when targeting known services.

---

🧪 Combine with TCP Scan

```
sudo nmap -sS -sU -p T:22,80,443,U:53,161 192.168.1.1
```

Combines TCP SYN and UDP scans.

T: for TCP ports, U: for UDP ports.

---

⚡ Speed Up UDP Scans

UDP scans can be painfully slow. Here are some ways to optimize them:

```
sudo nmap -sU --top-ports 20 192.168.1.1
```

Scans only the top 20 most common UDP ports.

Great for quicker checks with high probability.

---

## 🌐 UDP Port States

| State           | Meaning                                                                 |
|------------------|--------------------------------------------------------------------------|
| `open`           | A service responded to the UDP packet.                                  |
| `open|filtered`  | No response — may be open or filtered (common result)                   |
| `closed`         | ICMP "port unreachable" received — port is closed                       |

---

🔍 Real Example

```
sudo nmap -sU -p 161 -sV scanme.nmap.org
```

Scans port 161 (SNMP) and tries to determine the service version.

---

## 🧪 Port Selection Syntax

| Format             | Example                         | Description                                   |
|--------------------|----------------------------------|-----------------------------------------------|
| Single Port        | `-p 80`                         | Scan port 80 only                             |
| Multiple Ports     | `-p 22,80,443`                  | Scan listed ports                             |
| Port Range         | `-p 1-100`                      | Scan ports 1 through 100                      |
| TCP & UDP Split    | `-p T:22,80,U:53,161`           | Scan TCP and UDP ports separately             |
| Top Ports          | `--top-ports 20`                | Scan top 20 most common ports                 |

---

> 🔒 Note: Many firewalls and routers silently drop UDP packets, making UDP scanning less reliable than TCP. Still, it’s a key part of a complete network reconnaissance.

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/2%20-%20Scan%20Types/1%20-%20TCP%20Scan.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/2%20-%20Scan%20Types/3%20-%20Stealth%20Scan.md">Next Page</a>
</p>
