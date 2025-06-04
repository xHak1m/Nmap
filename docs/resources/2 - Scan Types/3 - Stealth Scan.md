<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 🕵️ Stealth Scanning in Nmap

Stealth scans are designed to avoid detection by firewalls, intrusion detection systems (IDS), and intrusion prevention systems (IPS). The most commonly used stealth scan is the **TCP SYN scan**.

---

## ⚙️ SYN Scan (`-sS`) — The Classic Stealth Scan

```
sudo nmap -sS 192.168.1.1
```

Sends a TCP SYN packet.

If the port is open, it responds with SYN-ACK.

Nmap immediately resets the connection with RST — no full handshake.

Requires sudo for raw socket access.

✅ Faster and quieter than full TCP (-sT)
❌ Still detectable by modern IDS/IPS, but harder to trace

---

## 🔍 Port State Detection (via Stealth Scan)

| Response Type          | Port State | Description                                      |
|------------------------|------------|--------------------------------------------------|
| SYN-ACK                | open       | Target is listening; responds to SYN            |
| RST                    | closed     | Target is reachable but no service is listening |
| No response / ICMP     | filtered   | Packet filtered by firewall; no definitive reply|

---

## 🕵️ Why Use Stealth Scans

| Reason                         | Description                                                        |
|--------------------------------|--------------------------------------------------------------------|
| Lower Detection Risk           | SYN scans don't complete the TCP handshake                        |
| Faster Than Full TCP Scans     | Only partial connection is made                                   |
| Avoid Logging in Some Cases    | Some systems log full connections but ignore half-open SYNs       |
| Useful for Reconnaissance      | Helps identify open ports silently                                 |
| Good for IDS/IPS Evasion       | Many intrusion systems fail to catch stealth scans completely      |

---

🔄 Combine with Other Options

```
sudo nmap -sS -p 1-1000 -v 192.168.1.1
```

Scans top 1000 ports with verbose output.

```
sudo nmap -sS -A scanme.nmap.org
```

Stealth scan + OS detection, version detection, script scan.

---

## ✅ Stealth Scan Summary

| Option     | Description                   |
|------------|-------------------------------|
| `-sS`      | SYN scan (stealth scan)       |
| `-p`       | Specify target port(s)        |
| `-T4`      | Faster timing (use cautiously)|
| `-v`       | Verbose mode                  |
| `-A`       | Combines with OS and version  |
| `--reason` | Shows why Nmap reports states |

---

> 🧠 Note: While stealth scans are quieter than full TCP scans, they’re not invisible. Use them responsibly and legally!

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/2%20-%20Scan%20Types/1%20-%20TCP%20Scan.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/2%20-%20Scan%20Types/4%20-%20Aggressive%20Scan.md">Next Page</a>
</p>
