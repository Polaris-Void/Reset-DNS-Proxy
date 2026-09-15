<p align="right">
  <a href="README.fa.md"> <strong>فارسی</strong></a>
</p>

---

# Network Troubleshooter: DNS & Proxy Reset

A lightweight, automated Windows batch utility designed to fix common network connectivity issues by resetting DNS server settings to DHCP, disabling system-wide proxies, and clearing the local DNS resolver cache.

Often, VPN clients, proxy tools (e.g., v2ray, Clash, Outline), anti-censorship software, or unexpected network crashes leave behind modified proxy configurations and static DNS addresses. These leftover settings prevent your browser and apps from accessing the internet. This script fixes all of them in a single click.

---

## ✨ Features

- **🔑 Automatic Elevation (UAC):** Checks for administrator privileges using `fsutil` and automatically prompts the UAC dialog via PowerShell if elevated rights are needed.
- **🌐 Reset DNS to DHCP:** Clears static or stuck DNS servers across **all** network adapters and resets them to automatic (DHCP) via PowerShell (`Get-NetAdapter | Set-DnsClientServerAddress -ResetServerAddresses`).
- **🚫 Disable System Proxy:** Forces `ProxyEnable = 0` in both User (`HKCU`) and System-wide (`HKLM`) Windows Registry locations to remove hanging proxy connections.
- **🧹 Flush DNS Cache:** Clears the Windows DNS resolver cache (`ipconfig /flushdns`) to apply changes immediately without requiring a system reboot.
- **⚡ Fast, Native & Clean:** Uses 100% built-in Windows tools (Batch & PowerShell) with clear status tags (`[+]`, `[-]`).

---

## 📋 Common Use Cases

- **"No Internet" after closing VPN/Proxy:** The VPN closed, but left the system proxy turned on.
- **Browser Errors:** You encounter `ERR_PROXY_CONNECTION_FAILED` or `DNS_PROBE_FINISHED_NO_INTERNET`.
- **Stuck DNS:** Network adapters are pointing to unreachable or dead DNS servers.

---

## 🚀 How to Use

1. Download or clone this repository.
2. Make sure the script file is saved with the `.bat` extension (e.g., `Reset-DNS-Proxy.bat`).
3. **Double-click** the script to run it.
4. If prompted by **User Account Control (UAC)**, click **Yes**.
5. The script will execute all steps automatically.
6. Once you see `All tasks completed successfully.`, press any key to close the window.

---

## 💻 System Requirements

- **OS:** Windows 8.1, Windows 10, or Windows 11 (32-bit & 64-bit).
- **PowerShell:** Version 5.0 or later (pre-installed on Windows 10 & 11).
- **Permissions:** Administrator access (requested automatically by the script).

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
