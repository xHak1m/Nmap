<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 🔓 Find Open Ports with Nmap

Finding open ports on a target system is one of the most essential tasks in network reconnaissance. Nmap gives multiple ways to detect them accurately and efficiently.

---

## ✅ Basic TCP Port Scan (Top 1000)

```bash
nmap <target>
```

| Option         | Description                                      |
|----------------|--------------------------------------------------|
| `<target>`     | IP address or hostname of the system             |
| No flags       | Scans top 1000 TCP ports by default              |

---

🎯 Scan Specific Ports

```
nmap -p 21,22,80 <target>
```

| Option     | Description                            |
|------------|----------------------------------------|
| `-p`       | Specifies exact ports to scan          |
| `21,22,80` | Common ports: FTP, SSH, HTTP           |

---

🔄 Scan a Port Range

```
nmap -p 1-65535 <target>
```

| Option      | Description                      |
|-------------|----------------------------------|
| `-p 1-65535`| Scan all 65,535 TCP ports        |
| Slower scan | Use with caution on large hosts  |

---

⚡ Faster Port Scan (No Service Detection)

```
nmap -T4 -F <target>
```

| Option | Description                                |
|--------|--------------------------------------------|
| `-T4`  | Faster timing (less accuracy/stealth)      |
| `-F`   | Fast mode — scans fewer than 100 ports     |

---

🛠 Stealth SYN Scan for Open Ports

```
sudo nmap -sS <target>
```

| Option    | Description                  |
|-----------|------------------------------|
| `-sS`     | Stealth SYN scan             |
| Needs sudo | Required on most systems     |

---

📄 Save Results to File

```
nmap -p 1-1000 -oN open_ports.txt <target>
```

| Option           | Description                         |
|------------------|-------------------------------------|
| `-oN`            | Save normal output to a file        |
| `open_ports.txt` | Name of the output file             |

---

✅ Summary

| Task                          | Command Example                         |
|-------------------------------|------------------------------------------|
| Scan top 1000 TCP ports       | `nmap 192.168.1.10`                     |
| Scan specific ports           | `nmap -p 22,80,443 192.168.1.10`        |
| Scan all TCP ports            | `nmap -p 1-65535 192.168.1.10`          |
| Fast scan (fewer ports)       | `nmap -T4 -F 192.168.1.10`              |
| Stealth SYN scan              | `sudo nmap -sS 192.168.1.10`            |
| Save scan result to file      | `nmap -p 1-1000 -oN open_ports.txt 192.168.1.10` |

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/4%20-%20Real%20World%20Examples/1%20-%20Scan%20a%20Network.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/4%20-%20Real%20World%20Examples/3%20-%20Detect%20OS%20%26%20Services.md">Next Page</a>
</p>
