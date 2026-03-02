# Syscheck Dashboard 🚀
![Dashboard Preview](preview.png)

A lightweight, high-visibility system dashboard for Fedora 43 Cloud, optimized for mobile SSH. Designed for the "Imperator" node.

## 🏗 Architecture: The "Sudo-Aware" Model
The project uses a hybrid architecture designed to bridge the gap between root-level security logs and user-level rootless containers:
* **Python Engine (`syscheck-engine`)**: Detects the `${SUDO_USER}` to query **Rootless Podman** sockets even when executed via sudo. Handles vnStat 2.13 SQLite parsing and real-time traffic deltas.
* **Bash Display (`syscheck`)**: A location-agnostic wrapper that finds its own directory and renders a 15-character wide UI optimized for Termux/Mobile SSH.

## 🛠 Features
- **Fastfetch Integration**: OS branding and system specs.
- **Dynamic Resource Bars**: RAM, Disk, and Log usage (2GB cap tracking).
- **Billing Quota**: Tracks a **750 GB monthly budget** (Reset: 13th).
- **Security Jails**: Live tracking of **Fail2Ban** (SSH, Recidive, Jitsi-Auth).
- **Terraria Live Stats**: Real-time player count and dynamic FPS based on CPU load.
- **Service Heartbeats**: HTTP status tracking for Caddy, HedgeDoc, and AdGuard.

## 📦 Requirements
- `python3`, `fastfetch`, `vnstat`, `fail2ban`, `podman`, `tailscale`

## 🚀 Execution
```bash
# Add this alias to your .bashrc
alias syscheck='sudo ~/syscheck-project/syscheck'
