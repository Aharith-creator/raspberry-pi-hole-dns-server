Network-Wide DNS Sinkhole with Pi-hole
A headless, network-wide DNS ad blocker and tracker filter deployed on a Raspberry Pi 2 Model B running Raspberry Pi OS Lite (32-bit).

Hardware & Software Stack
Hardware: Raspberry Pi 2 Model B (900MHz Quad-Core ARMv7, 1GB RAM)
Power Supply: Dedicated 5V 2.5A Micro-USB power adapter (preventing undervoltage during 24/7 operation)
Network Connection: Wired RJ45 Ethernet to home router
Operating System: Raspberry Pi OS Lite (32-bit)
Software: Pi-hole DNS Sinkhole, OpenSSH

Network Architecture
[Client Devices] ---> [Home Router (DHCP/DNS)] ---> [Raspberry Pi 2 (Pi-hole)] ---> [Upstream DNS (1.1.1.1)]


Deployment Workflow
Storage Verification on Linux: Used lsblk, dmesg, and f3probe to verify microSD card device paths and genuine flash storage capacity prior to flashing.
Headless OS Flashing: Flashed Raspberry Pi OS Lite (32-bit) via Raspberry Pi Imager with SSH password authentication pre-configured.
Static IP & System Updates: Reserved a static IP address for the Raspberry Pi in the router's DHCP table and updated system packages via SSH (sudo apt update && sudo apt upgrade -y).
Pi-hole Installation: Installed Pi-hole via curl -sSL https://pi-hole.net | bash and configured Cloudflare (1.1.1.1) as the upstream DNS resolver.
Router DNS Cutover: Pointed the router's primary DNS server to the Pi-hole's local static IP to filter ads and telemetry across all connected devices.

Key Skills Demonstrated
Linux CLI & Block-Device Diagnostics (lsblk, dmesg, f3probe)
Headless Server Provisioning & Remote Administration (SSH)
Network Protocols & Infrastructure (DNS, DHCP Reservations, Static IP Routing)
Technical Documentation & Version Control (Git, GitHub, Markdown)

