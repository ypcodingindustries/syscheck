# Syscheck Dashboard 🚀
![Dashboard Preview](preview.png)

A lightweight, high-visibility system dashboard for Fedora Cloud, optimized for mobile SSH. Designed for the "Imperator" node.

## 🏗 Architecture: The "Split Engine" Model
The project uses a hybrid architecture to ensure stability on narrow mobile screens:
* **Python Engine (`syscheck-engine`)**: Handles the heavy lifting—SQLite database parsing (vnStat 2.13), delta-math (Traffic), and service heartbeats. It outputs a single pipe-delimited string to prevent "ghost characters" and line-wrapping bugs.
* **Bash Display (`syscheck`)**: Handles the aesthetic—renders the UI, dynamic progress bars with "round-up" logic for low values, and high-visibility colors.

## 🛠 Features
- **Fastfetch Integration**: Clean system info and OS branding.
- **Dynamic Resource Bars**: Visual RAM, Disk, and Quota usage optimized for 15-char mobile width with alignment-correction.
- **Billing Cycle Tracking**: Optimized for vnStat 2.13 to track a **750 GB monthly budget** resetting on the **13th** of every month.
- **Security & Jails**: Live tracking of **Fail2Ban** hits across **SSH, Recidive, and Jitsi** auth jails. Includes systemd security exposure analysis.
- **Service Heartbeat**: 
    - **Jitsi & Send**: Status tracking for containerized services and systemd units.
    - **Caddy, HedgeDoc, & AdGuard**: Real-time status tracking via HTTP response codes (Credential-free for security).
    - **Tailscale Exit Node**: Detects if the VPS is advertising itself as an exit node (integrated with `vpn-flip`).
- **Network Carnage**: Real-time RX/TX traffic sampling and Tailscale/Global IP tracking.

## 📦 Dependencies
Ensure these are installed on your Fedora system:
- `python3` (for the data engine)
- `fastfetch` (for the header)
- `vnstat` (v2.10+ required for SQLite support)
- `tailscale` (for VPN/Exit Node status)
- `fail2ban` (for security jail tracking)

## 🚀 Installation & Configuration
1. Clone this repo: `git clone https://github.com/ypcodingindustries/syscheck.git ~/syscheck-project`
2. Create an alias: `echo "alias syscheck='~/syscheck-project/syscheck'" >> ~/.bashrc`
3. **Configure vnStat Billing Cycle**:
   Edit `/etc/vnstat.conf` and set `MonthRotate DATE` to match the provider billing cycle.
4. Run the dashboard: `syscheck`
