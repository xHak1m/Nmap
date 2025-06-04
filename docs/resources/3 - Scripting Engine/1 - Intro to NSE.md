<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 🧠 Nmap Scripting Engine (NSE) Introduction

The **Nmap Scripting Engine (NSE)** allows users to write and run custom scripts that automate network scanning, vulnerability detection, brute-forcing, and more.

NSE makes Nmap a **powerful security tool** beyond simple port scanning.

---

## 📚 What Is NSE?

NSE uses **Lua scripts** stored in Nmap’s `scripts/` directory. Scripts can be run against targets to extend Nmap’s capabilities.

There are **over 600+** built-in scripts included with Nmap.

---

## 🧰 NSE Script Categories

| Category        | Description                                                             |
|-----------------|-------------------------------------------------------------------------|
| `auth`          | Brute-force and authentication bypass                                  |
| `default`       | Run with `-sC` or `-A` (basic discovery)                               |
| `discovery`     | Host and service discovery                                              |
| `exploit`       | Exploits known vulnerabilities                                          |
| `intrusive`     | High-impact scripts that may crash services                            |
| `malware`       | Checks for malware or backdoors                                        |
| `safe`          | Scripts considered safe for production systems                         |
| `vuln`          | Detects known vulnerabilities                                           |
| `version`       | Enhances service version detection                                      |

---

## 🛠️ Running Scripts

| Command                         | Description                                      |
|----------------------------------|--------------------------------------------------|
| `nmap --script default`         | Runs default scripts                             |
| `nmap --script vuln`            | Runs vulnerability detection scripts             |
| `nmap --script http-*`          | Runs all HTTP-related scripts                    |
| `nmap --script-help <script>`   | Displays help for a specific script              |
| `nmap --script <script1,script2>` | Runs multiple named scripts                    |

---

## 📝 Example Commands

```bash
nmap -sV --script default 192.168.1.1
```

Version detection + default scripts

```
nmap --script vuln -p 80,443 192.168.1.1
```

Checks for web-related vulnerabilities

```
nmap --script ftp-anon 192.168.1.1
```

Checks if FTP allows anonymous login

---

## ✅ NSE Summary

| Feature           | Value / Description                                    |
|-------------------|--------------------------------------------------------|
| Language          | Lua                                                    |
| Script Count      | 600+ built-in scripts                                  |
| Script Categories | `auth`, `vuln`, `discovery`, `exploit`, etc.           |
| Script Location   | `/usr/share/nmap/scripts/` (Linux)                     |
| Run with Option   | `--script`                                             |
| Combine With      | `-sV`, `-A`, `-p`                                       |
| Help Command      | `--script-help <script-name>`                          |

---

> 🔐 Pro Tip: Use --script-help to see script usage, risk level, and category before running anything on a live system.

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/2%20-%20Scan%20Types/4%20-%20Aggressive%20Scan.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/3%20-%20Scripting%20Engine/2%20-%20Useful%20Scripts.md">Next Page</a>
</p>
