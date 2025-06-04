<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 🧠 Detect OS and Services with Nmap

Nmap can go beyond port scanning and detect the **operating system**, **running services**, and their **versions**. This is useful for vulnerability assessments, network audits, and pentesting.

---

## ✅ OS Detection

```bash
sudo nmap -O <target>
```

| Option | Description                              |
|--------|------------------------------------------|
| `-O`   | Enables OS detection                     |
| `sudo` | Required for OS fingerprinting on most systems |

---

🔍 Service Version Detection

```
nmap -sV <target>
```

| Option | Description                            |
|--------|----------------------------------------|
| `-sV`  | Probes ports to detect service versions |

---

🎯 Combine OS and Service Detection

```
sudo nmap -sV -O <target>
```

| Option | Description                                 |
|--------|---------------------------------------------|
| `-sV`  | Detects service versions                    |
| `-O`   | OS fingerprinting                           |
| `sudo` | Required for accurate OS detection          |

---

⚡ Aggressive Scan for OS + Services + More

```
sudo nmap -A <target>
```

| Option | Description                                       |
|--------|---------------------------------------------------|
| `-A`   | Enables OS detection, service/version, scripts, and traceroute |
| `sudo` | Required for some OS and traceroute features      |

---

📝 Notes

OS detection is based on TCP/IP stack fingerprinting.

Service detection sends custom probes to ports to identify software.

Not all OS detections are accurate — Nmap provides an accuracy score.

---

✅ Summary

| Task                        | Command Example                 |
|-----------------------------|----------------------------------|
| Detect OS                   | `sudo nmap -O 192.168.1.10`     |
| Detect service versions     | `nmap -sV 192.168.1.10`         |
| OS + Service detection      | `sudo nmap -sV -O 192.168.1.10` |
| Aggressive full detection   | `sudo nmap -A 192.168.1.10`     |

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/4%20-%20Real%20World%20Examples/2%20-%20Find%20Open%20Ports.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/5%20-%20Cheat%20Sheets/Nmap%20Cheat%20Sheets.md">Next Page</a>
</p>
