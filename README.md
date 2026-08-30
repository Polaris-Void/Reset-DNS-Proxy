# Reset DNS Proxy

A lightweight, automated Windows Batch script designed to resolve internet connectivity issues by resetting DNS configurations to automatic (DHCP), disabling system proxies, and clearing the local DNS cache.

## Features

- **Automatic Privilege Elevation:** Prompts for Administrator rights (UAC) automatically if executed without elevation.
- **DNS Configuration Reset:** Restores DNS settings to automatic (DHCP) across all network adapters via integrated PowerShell execution.
- **System Proxy Disablement:** Clears system proxy settings in both `HKCU` and `HKLM` registry paths.
- **DNS Cache Clearance:** Flushes the DNS resolver cache to enforce immediate network routing updates.

## Requirements

- Operating System: Windows 10 or Windows 11
- User Privileges: Administrator access

## Installation and Execution

1. Download the `Reset DNS Proxy.bat` file from the repository.
2. Run the script:
   - Double-click `Reset DNS Proxy.bat` and accept the UAC prompt, or
   - Right-click the file and select **Run as administrator**.
3. Wait for the execution process to complete and test your internet connection.

> **Note:** If executing via Command Prompt (CMD), wrap the file name in quotation marks due to spaces:
> ```cmd
> "Reset DNS Proxy.bat"
> ```

## Technical Details

The script executes the following operations in sequence:

1. Checks administrative status using `fsutil dirty query %systemdrive%`.
2. Invokes PowerShell to reset DNS client server addresses:
   ```powershell
   Get-NetAdapter | Set-DnsClientServerAddress -ResetServerAddresses
