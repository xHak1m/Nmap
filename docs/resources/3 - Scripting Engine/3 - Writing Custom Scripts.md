<p align="center">
	<img src="https://raw.githubusercontent.com/xHak1m/Nmap/main/docs/images/nmap.png" width=500alt="nmap.png"/>
</p>

---

# 🛠️ Writing Custom Nmap Scripts (NSE)

The Nmap Scripting Engine (NSE) lets you write your own scripts using **Lua** to automate scans, exploit vulnerabilities, or extend Nmap’s behavior.

This guide walks you through the basics of creating and using custom scripts.

---

## ❓ Why Write Custom Scripts?

| Reason                    | Description                                                    |
|---------------------------|----------------------------------------------------------------|
| Custom Recon              | Automate info-gathering tasks for your environment             |
| Exploit or Bypass Logic   | Add logic not available in existing NSE scripts                |
| Automate Repetitive Scans | Run custom logic for large-scale or routine assessments        |
| Share with Others         | Create useful tools for your team or security community        |

---

## 🧱 Basic Script Structure

```lua
description = [[
  Example NSE script that scans and prints port info.
]]

author = "YourName"

license = "Same as Nmap--See https://nmap.org/book/man-legal.html"

categories = {"default"}

-- Rule: when to run the script
portrule = function(host, port)
  return port.protocol == "tcp" and port.state == "open"
end

-- Action: what the script does
action = function(host, port)
  return "Scanned port: " .. port.number
end
```

---

## 🔑 Key Fields in NSE Scripts

| Field        | Purpose                                            |
|--------------|----------------------------------------------------|
| `description`| Explains what the script does                      |
| `author`     | Your name or handle                                |
| `license`    | Script licensing (usually same as Nmap’s license)  |
| `categories` | NSE tags: `default`, `vuln`, `auth`, etc.          |
| `portrule`   | When to run the script (usually checks port state) |
| `action`     | Main function that runs if portrule passes         |

---

## 📁 Where to Save Your Script

| Path                                | Description                                      |
|-------------------------------------|--------------------------------------------------|
| `/usr/share/nmap/scripts/`         | Global scripts (root access required)            |
| `~/.nmap/scripts/`                 | Per-user script location (no root required)      |

After saving, run this to update the script database:

```
sudo nmap --script-updatedb
```

---

▶️ How to Run Your Script

```
nmap -p 80 --script ./your-script.nse <target>
```

Or if saved in the default folder:

```
nmap -p 80 --script your-script <target>
```

---

## ✅ Custom Script Tips

| Tip                         | Details                                                             |
|-----------------------------|---------------------------------------------------------------------|
| Use `stdnse.print_debug()`  | Output debug info during testing                                   |
| Use `nmap.registry`         | Share data between scripts                                         |
| Use `nmap.new_socket()`     | Create raw, UDP, or TCP socket connections                         |
| Use helper libraries        | NSE includes many libraries in `/nselib/` for protocols like HTTP  |
| Test with `--script-trace`  | Shows raw script network activity for debugging                    |

---

📚 Learn More

- Official NSE Guide: https://nmap.org/book/nse.html

- Script Index: https://nmap.org/nsedoc/

- Sample Scripts: /usr/share/nmap/scripts/

> 🧠 NSE is powerful. With Lua, you can automate anything from version detection to exploiting backdoors.

---

<p align="center">
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/3%20-%20Scripting%20Engine/2%20-%20Useful%20Scripts.md">Previous Page</a> • 
	<a href="https://github.com/xHak1m/Nmap/blob/main/docs/resources/4%20-%20Real%20World%20Examples/1%20-%20Scan%20a%20Network.md">Next Page</a>
</p>
