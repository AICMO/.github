# AICMO

AI-powered content curation and publishing infrastructure.

## One-Click Server Setup

[`hetzner-setup.sh`](https://github.com/AICMO/Autonomous-Agent-Digests-Blog/blob/main/infra/hetzner-setup.sh) — provisions a fully hardened Ubuntu server accessible only via Tailscale. No SSH exposed on public IP.

**Connection stack:** Tailscale + Mosh/SSH + Termius + sshid.io hardware keys

What you get:
- Ubuntu 24.04 with unattended security upgrades (auto-reboot at 02:00)
- Tailscale mesh VPN (private SSH + Mosh access)
- Docker Engine + Compose plugin
- Mosh, curl, jq, tmux, git
- Hetzner HW firewall (80/443 only, no public SSH)
- UFW: Cloudflare-only HTTP/S (default) + all traffic on tailscale0
- SSH bound to Tailscale IP only (key-only, no root, no passwords)
- fail2ban, sysctl hardening, 180-day log retention
- sshid.io hardware keys for Termius mobile access
- Ephemeral Tailscale node (auto-removed on server destroy)

<img width="64" height="64" alt="termius-icon-64" src="https://github.com/user-attachments/assets/39b29ec3-19c2-46d9-abd7-e2ca0dbb4d58" /> Termius provides a secure, reliable, and collaborative SSH client.

