
# Syscheck Dashboard 🚀

![Dashboard Preview](preview.png)

A lightweight, high-visibility system dashboard for Fedora Cloud, optimized for mobile SSH. Designed for the "Imperator" node.

## 🛠 Features
- **Fastfetch Integration**: Clean system info and OS branding.
- **Resource Bars**: Visual RAM, CPU, and Disk usage progress bars.
- **Node Life & Quota**: Tracking server age and daily bandwidth limits.
- **Security Carnage**: Live tracking of Fail2Ban hits, Recidive bans, and SSH threats.
- **Service Heartbeat**: 
    - **Caddy**: Web server status via Admin API.
    - **HedgeDoc**: Documentation server health tracking.
    - **AdGuard Home**: Live DNS block counts and filtering efficiency percentage.
- **Network Stats**:
    - **Tailscale**: Internal Mesh IP tracking.
    - **Traffic**: Real-time Up/Down bandwidth monitoring.

## 🚀 Installation
1. Clone this repo to `~/syscheck-project`.
2. Link the script: `sudo ln -s $(pwd)/syscheck /usr/local/bin/syscheck`.
3. Set your AdGuard credentials in the script header.
4. Ensure `vnstat` and `bc` are installed for bandwidth tracking.

## ⚡ Optional Power-Ups
Add these to your \`~/.bashrc\` to unlock live monitoring and easy backups:

### 1. Live Dashboard Mode
Watch your system stats update in real-time (1s refresh):
\`\`\`bash
alias longwatch='watch -n 1 -c ~/syscheck-project/syscheck'
\`\`\`

### 2. Quick Cloud Save
Backup your script tweaks to Git from any directory:
\`\`\`bash
alias gitsave='cd ~/syscheck-project && git add . && git commit -m "Update" && git push origin main && cd -'
\`\`\`


