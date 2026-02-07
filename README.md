# Syscheck Dashboard 🚀

![Dashboard Preview](preview.png)

A lightweight, high-visibility system dashboard for Fedora Cloud, optimized for mobile SSH. Designed for the "Imperator" node.

## 🛠 Features
- **Fastfetch Integration**: Clean system info and OS branding.
- **Resource Bars**: Visual RAM, CPU, and Disk usage progress bars.
- **Security Carnage**: Live tracking of Fail2Ban hits and repeat offenders.
- **Service Heartbeat**: 
    - **Caddy**: Web server status via Admin API.
    - **HedgeDoc**: Documentation server health tracking.
    - **AdGuard Home**: Live DNS block counts and filtering efficiency.
- **Network Stats**: 
    - **Tailscale**: Internal Mesh IP and active peer detection.
    - **Traffic**: Real-time Up/Down bandwidth monitoring.

## 🚀 Installation
1. Clone this repo to `~/syscheck-project`.
2. Link the script: `sudo ln -s $(pwd)/syscheck /usr/local/bin/syscheck`.
3. Set your AdGuard credentials in the script header.
4. Ensure `httpd-tools` is installed for password hashing if needed: `sudo dnf install httpd-tools`.

## 📱 Mobile Use
This dashboard is specifically formatted for narrow-width mobile SSH terminals (like Termux or iOS Shell).
