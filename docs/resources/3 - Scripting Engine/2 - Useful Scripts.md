<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 🔧 Useful Nmap Scripts (NSE)

Nmap’s scripting engine offers powerful built-in scripts for information gathering, vulnerability detection, and exploitation.

Below are some of the most commonly used and effective scripts sorted by category.

---

## 🌐 HTTP / Web Scripts

| Script Name       | Description                                       | Usage Example                      |
|-------------------|---------------------------------------------------|------------------------------------|
| `http-title`      | Gets title of website                            | `--script http-title`             |
| `http-enum`       | Enumerates directories and files                 | `--script http-enum`              |
| `http-methods`    | Lists allowed HTTP methods                       | `--script http-methods`           |
| `http-headers`    | Dumps HTTP headers                               | `--script http-headers`           |
| `http-vuln-cve2017-5638` | Checks for Apache Struts vulnerability | `--script http-vuln-cve2017-5638` |

---

## 📁 FTP Scripts

| Script Name       | Description                                       | Usage Example                      |
|-------------------|---------------------------------------------------|------------------------------------|
| `ftp-anon`        | Checks for anonymous FTP login                   | `--script ftp-anon`               |
| `ftp-bounce`      | Tests for FTP bounce attack support              | `--script ftp-bounce`             |
| `ftp-syst`        | Gets FTP system info                             | `--script ftp-syst`               |

---

## 🖥️ SMB / Windows Scripts

| Script Name         | Description                                    | Usage Example                     |
|---------------------|------------------------------------------------|-----------------------------------|
| `smb-os-discovery`  | Gets Windows version and hostname              | `--script smb-os-discovery`      |
| `smb-enum-shares`   | Lists shared folders                           | `--script smb-enum-shares`       |
| `smb-vuln-ms17-010` | Checks for EternalBlue vulnerability           | `--script smb-vuln-ms17-010`     |

---

## 🔐 SSH Scripts

| Script Name     | Description                                      | Usage Example                   |
|-----------------|--------------------------------------------------|---------------------------------|
| `ssh-hostkey`   | Retrieves SSH host keys                         | `--script ssh-hostkey`         |
| `sshv1`         | Detects support for deprecated SSHv1            | `--script sshv1`               |

---

## 🔑 Authentication & Brute Force

| Script Name        | Description                                     | Usage Example                      |
|--------------------|-------------------------------------------------|------------------------------------|
| `ftp-brute`        | Brute-force FTP login                           | `--script ftp-brute`              |
| `ssh-brute`        | Brute-force SSH login                           | `--script ssh-brute`              |
| `http-form-brute`  | Brute-forces web login forms                    | `--script http-form-brute`        |

---

## 📌 Notes

- Use `--script-help <script-name>` to learn about what each script does and what ports it needs.
- Combine scripts with version detection: `-sV --script <name>` for best results.
- Be careful with **intrusive** scripts — they can crash or alert systems.

---

> ⚠️ **Tip:** Run `ls /usr/share/nmap/scripts/` to browse all installed scripts.

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/3%20-%20Scripting%20Engine/1%20-%20Intro%20to%20NSE.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/3%20-%20Scripting%20Engine/3%20-%20Writing%20Custom%20Scripts.md">Next Page</a>
</p>
