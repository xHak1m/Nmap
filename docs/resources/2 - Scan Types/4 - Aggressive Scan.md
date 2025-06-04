<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 🚨 Aggressive Scanning in Nmap (`-A`)

The `-A` option in Nmap enables aggressive scanning, combining multiple advanced techniques into one powerful scan. It's great for information gathering but should be used with care to avoid detection or unintended disruption.

---

## 🔧 What Does `-A` Include?

| Feature             | Equivalent Option | Description                                  |
|---------------------|-------------------|----------------------------------------------|
| OS Detection        | `-O`              | Attempts to identify the target OS           |
| Version Detection   | `-sV`             | Detects service versions                     |
| Script Scanning     | `-sC`             | Runs default NSE scripts                     |
| Traceroute          | —                 | Maps the network path to the target          |

---

## 🛡️ Why Use Aggressive Scans

| Purpose                    | Description                                                              |
|----------------------------|--------------------------------------------------------------------------|
| Full Reconnaissance        | Collects deep info on OS, services, and network layout                   |
| Vulnerability Discovery    | Detects known issues through scripts and version info                   |
| Penetration Testing Prep   | Essential first step before exploiting targets                           |
| Fast Security Audits       | Quickly reveals misconfigurations and attack surfaces                    |

---

🧪 What It Reveals

- Operating system and device type

- Software/services running on each port

- Service versions

- Known vulnerabilities (via scripts)

- Network path (traceroute)

---

## ⚠️ Risks of Using `-A`

| Risk                       | Description                                                              |
|----------------------------|---------------------------------------------------------------------------|
| Easily Detected            | Sends many packets, triggers IDS/IPS                                      |
| Can Disrupt Services       | Some fragile systems may crash or slow down                               |
| Legal Implications         | Scanning unauthorized targets can be illegal                              |
| Slower Than Simple Scans   | Combines multiple scan types into one                                     |

---

## ✅ Aggressive Scan Summary

| Option     | Description                                               |
|------------|-----------------------------------------------------------|
| `-A`       | Enables aggressive scan (OS, version, scripts, traceroute)|
| `-T4`      | Speeds up scan (use cautiously)                           |
| `-v`       | Verbose output                                            |
| `-Pn`      | Treat host as online (skip ping check)                   |
| `-p-`      | Scan all 65535 ports (optional)                           |

---

🔍 Example Command

```
sudo nmap -A -T4 scanme.nmap.org
```

Runs aggressive scan with faster timing on a legal test target.

---

> 🧠 Note: Use aggressive scans responsibly. Avoid running them on targets without permission — they are loud and can cause alarm on production systems.

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/2%20-%20Scan%20Types/3%20-%20Stealth%20Scan.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/3%20-%20Scripting%20Engine/1%20-%20Intro%20to%20NSE.md">Next Page</a>
</p>
