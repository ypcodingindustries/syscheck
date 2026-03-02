# Imperator Node Recovery Prompt 🛠️

Use this prompt when starting a new session with an AI to restore or troubleshoot the VPS.

## Context
- **OS:** Fedora 43 Cloud (KVM/QEMU)
- **User:** Rootless 'Firegod' (UID 1000) with lingering enabled.
- **Monitoring:** Split-model (Python engine + Bash UI).
- **Network:** Dual-stack IPv4/v6, Tailscale Exit Node, vnStat 2.13 (750GB quota / 13th reset).
- **Containers:** Rootless Podman (Jitsi, AdGuard, Terraria).

## Hard Constraints
1. **NO HOST MODE:** Never bypass container isolation for Jitsi or any other service. Use slirp4netns or clear rootless-netns if bridge creation fails.
2. **NO STRIPPING LOGIC:** Do not remove quota math, Fail2Ban jails, or Terraria FPS/User stats to "simplify" the script.
3. **MOBILE UI:** All progress bars must be 15-char width. Use pipe-delimited strings for the engine-to-UI handoff.
4. **CAT BLOCKS:** Provide all code in 'cat << EOF' blocks for mobile-friendly copy-pasting.
