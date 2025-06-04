<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 🌐 Scan a Network with Nmap

Scanning an entire network is one of the most common uses of Nmap. This allows you to identify live hosts, open ports, operating systems, and services across all devices in a subnet.

---

## ✅ Basic Network Scan

```
nmap 192.168.1.0/24
```

| Option             | Description                            |
|--------------------|----------------------------------------|
| `192.168.1.0/24`   | CIDR notation for scanning all 256 IPs |
| No flags           | Just checks which hosts are up         |

---

🔍 Scan All Devices with Port and Service Detection

```
nmap -sS -sV 192.168.1.0/24
```

| Option   | Description                         |
|----------|-------------------------------------|
| `-sS`    | Stealth SYN scan                    |
| `-sV`    | Service version detection           |
| `/24`    | Scans full subnet (192.168.1.0–255) |

---

🧠 Identify Operating Systems in the Network

```
sudo nmap -O 192.168.1.0/24
```

| Option | Description                             |
|--------|-----------------------------------------|
| `-O`   | Attempts OS fingerprinting (needs sudo) |

> ⚠️ OS detection may not always succeed, especially on firewalled devices.

---

💡 Best Practice: Combine Everything

```
sudo nmap -sS -sV -O -Pn 192.168.1.0/24
```

| Option | Description                            |
|--------|----------------------------------------|
| `-Pn`  | Treat all hosts as up (skip ping)      |
| `-sS`  | SYN stealth scan                       |
| `-sV`  | Detect service versions                |
| `-O`   | OS detection                           |

---

📝 Notes

You can change 192.168.1.0/24 to any subnet: e.g., 10.0.0.0/16, 172.16.5.0/24.

If scanning public networks, ensure you have permission — unauthorized scanning can get you blocked or reported.

---

✅ Summary

| Task                         | Command Example                            |
|------------------------------|---------------------------------------------|
| Ping all devices             | `nmap 192.168.1.0/24`                      |
| Stealth scan with services   | `nmap -sS -sV 192.168.1.0/24`              |
| OS fingerprinting            | `sudo nmap -O 192.168.1.0/24`              |
| Full recon                   | `sudo nmap -sS -sV -O -Pn 192.168.1.0/24`  |

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/3%20-%20Scripting%20Engine/3%20-%20Writing%20Custom%20Scripts.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/4%20-%20Real%20World%20Examples/2%20-%20Find%20Open%20Ports.md">Next Page</a>
</p>
