<p align="right">
  <a href="README.fa.md"> <strong>فارسی</strong></a>
</p>

---

# 🌐 Network Troubleshooter — DNS & Proxy Reset

A lightweight, automated Windows batch script designed to quickly resolve internet connectivity, DNS hijacking, and proxy routing issues with a single click.

---

## 🧐 Why This Tool?

One of the most common reasons for sudden internet loss in Windows occurs when:
- A **VPN or proxy tool** crashes or is uninstalled while leaving the Windows system proxy turned on.
- A custom, stale, or poisoned **DNS server** prevents domain names from resolving.
- Windows keeps cached bad DNS records in the local resolver.

This utility automates the entire repair process using **100% native Windows tools**—no third-party software required.

---

## ✨ Features

- 🔑 **Automatic Elevation:** Detects administrative privileges via `fsutil` and automatically requests UAC elevation if needed.
- 🔄 **Universal DNS Reset:** Uses PowerShell's `NetTCPIP` cmdlets to automatically reset DNS addresses to default (DHCP) across **all** network adapters (Ethernet, Wi-Fi, etc.).
- 🚫 **System-Wide Proxy Disable:** Clears and disables proxy configurations at both the **User** (`HKCU`) and **System-wide Machine** (`HKLM`) registry levels.
- 🧹 **DNS Cache Flushing:** Flushes the Windows resolver cache (`ipconfig /flushdns`) to apply changes immediately without requiring a restart.
- 🪶 **Zero Dependencies:** Pure Batch and native PowerShell; safe, clean, and portable.

---

## 📋 System Requirements

- **OS:** Windows 8.1, Windows 10, or Windows 11 (32-bit & 64-bit)
- **PowerShell:** PowerShell 3.0 or higher (pre-installed on modern Windows)
- **Permissions:** Administrative rights (requested automatically on launch)

---

## 🚀 How to Use

1. Download or clone this repository.
2. Double-click **`Reset-DNS-Proxy.bat`**.
3. If prompted by **User Account Control (UAC)**, click **Yes** to grant administrative privileges.
4. Wait a few seconds until you see:
   ```text
   ==============================================================
                  All tasks completed successfully.
   ==============================================================
