<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 📌 Nmap Cheat Sheets

A quick reference guide to the most useful Nmap commands for scanning, detection, and scripting.

---

## 🔍 Basic Scans

```bash
nmap <target>
```

| Command                     | Description                          |
|-----------------------------|--------------------------------------|
| `nmap <IP>`                 | Scan top 1000 TCP ports              |
| `nmap -p 22,80 <IP>`        | Scan specific ports                  |
| `nmap -p 1-65535 <IP>`      | Scan all ports                       |
| `nmap -F <IP>`              | Fast scan (100 ports)                |

---

🎯 Stealth and Aggressive Scans

```
sudo nmap -sS <target>
```

| Command                     | Description                          |
|-----------------------------|--------------------------------------|
| `-sS`                       | Stealth SYN scan                     |
| `-sT`                       | Full TCP connect scan                |
| `-A`                        | Aggressive scan (OS, version, script, traceroute) |
| `-T4`                       | Faster timing                        |

---

🧠 OS and Service Detection

```
nmap -sV -O <target>
```

| Command                 | Description                          |
|-------------------------|--------------------------------------|
| `-sV`                   | Service/version detection            |
| `-O`                    | OS fingerprinting                    |
| `-A`                    | Aggressive scan (includes both)      |

---

🎭 Bypass Techniques

```
nmap -Pn <target>
```

🎭 Bypass Techniques Table

| Command                 | Description                          |
|-------------------------|--------------------------------------|
| `-Pn`                   | Skip host discovery (treat as alive) |
| `-f`                    | Fragment packets (evade firewalls)   |
| `--source-port 53`      | Use spoofed source port              |

---

📂 Output Formats

```
nmap -oN result.txt <target>
```

| Command             | Description                        |
|---------------------|------------------------------------|
| `-oN file.txt`      | Normal output                      |
| `-oX file.xml`      | XML output                         |
| `-oG file.gnmap`    | Grepable output                    |
| `-oA basename`      | Output in all formats              |

---

🛠 NSE Script Engine

```
nmap --script <script> <target>
```

| Command                                | Description                          |
|----------------------------------------|--------------------------------------|
| `--script default`                     | Run default scripts                  |
| `--script vuln`                        | Run vulnerability scripts            |
| `--script <category>`                  | Run specific category                |
| `--script-help <script>`               | Info about a specific script         |

---

✅ Common Summary

| Task                            | Example Command                          |
|----------------------------------|------------------------------------------|
| Fast scan                       | `nmap -F 192.168.1.1`                    |
| All TCP ports                   | `nmap -p 1-65535 192.168.1.1`            |
| Stealth scan                    | `sudo nmap -sS 192.168.1.1`              |
| Aggressive scan                 | `sudo nmap -A 192.168.1.1`               |
| OS and service detection        | `sudo nmap -sV -O 192.168.1.1`           |
| Run vulnerability scripts       | `nmap --script vuln 192.168.1.1`         |
| Save all output formats         | `nmap -oA scan_output 192.168.1.1`       |

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/4%20-%20Real%20World%20Examples/3%20-%20Detect%20OS%20%26%20Services.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/6%20-%20Legal%20Ethics/1%20-%20Responsible%20Usage.md">Next Page</a>
</p>
