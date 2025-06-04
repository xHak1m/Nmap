<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="Nmap"/>
</p>

---

# Installing Nmap

Installing Nmap is simple and supported across all major operating systems. Below are instructions for Linux, Windows, and macOS.

---

## 🐧 Linux

### Debian / Ubuntu
```
sudo apt update
sudo apt install nmap
```

Arch Linux / Manjaro
```
sudo pacman -S nmap
```

Fedora / RHEL / CentOS
```
sudo dnf install nmap
```
---

## 🪟 Windows

1. Visit the official Nmap download page.

2. Download the Windows installer.

3. Run the installer and follow the setup wizard.

4. Open the Command Prompt (cmd.exe) and type:

```
nmap -v
```

If it shows version info, Nmap is installed correctly.

✅ The Windows installer also includes Zenmap (the GUI frontend for Nmap).

---

## 🍎 macOS

There are a few different ways to install Nmap on macOS. The easiest and most common is using **Homebrew**.

## ✅ Method 1: Using Homebrew (Recommended)

### 🔹 Step-by-step:

# 1. Make sure Homebrew is installed
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

# 2. Install Nmap
```
brew install nmap
```

# 3. Verify installation
```
nmap --version
```

---

## ✅ Method 2: Without Homebrew:

Download the macOS installer from https://nmap.org/download.html

Mount the .dmg file and drag Nmap to your Applications folder

## ✅ Verifying the Installation

After installation, run:

```
nmap -v
```

You should see version info like:

```
Nmap version 7.94 ( https://nmap.org )
```

---

📌 Optional: Install Zenmap (GUI)

Zenmap is a graphical interface for Nmap. It’s useful for beginners to visualize scan results.

> Note: Zenmap is no longer maintained officially, but older versions still work on some systems.

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/1%20-%20Basic/1%20-%20What%20is%20Nmap.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/1%20-%20Basic/3%20-%20Basic%20Commands.md">Next Page</a>
</p>
