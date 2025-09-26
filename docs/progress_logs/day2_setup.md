# Day 2 – Hardware and VM Setup
**Date**: September 25, 2025

## Goals
- Install and configure pfSense VM
- Set up Ubuntu VM with static IP and services
- Configure OpenWrt AP and USB-C Ethernet
- Test network connectivity
- Update documentation

## Tasks Completed
- Installed Ubuntu VM with full server setup on September 25, 2025.
- Skipped initial network configuration during Ubuntu installation.
- Created and applied `/etc/netplan/00-installer-config.yaml` with static IP 192.168.1.2/24, gateway 192.168.1.1, and DNS 192.168.1.1, 8.8.8.8.
- Configured OpenWrt AP with LAN IP 192.168.1.5/24, disabled DHCP, set SSID "OpenHaus Free Wi-Fi (Demo)", and WPA2-PSK/WPA3-SAE security.
- Set up Openhaus USB-C Ethernet on MacBook with static IP 192.168.1.3/24, gateway 192.168.1.1, and DNS 192.168.1.1.
- Installed and configured pfSense VM with LAN 192.168.1.1/24, WAN via Bridged Wi-Fi, hostname "openhaus-pfsense", and DNS resolver enabled, with DHCP range 192.168.1.100-200.
- Verified connectivity with successful ping tests from Ubuntu VM to 192.168.1.1 (pfSense) and 192.168.1.5 (OpenWrt AP).
- Tested SSH service with successful login from MacBook to Ubuntu VM (`ssh openhaus@192.168.1.2`).
- Updated `/docs/setup_notes.md`, `/docs/project_overview.md`, `/docs/network_architecture.md`, and `/docs/progress_logs/day2_setup.md` with configuration details and screenshot references in `/docs/images/config/`.

## Issues / Challenges
- Missing `/etc/netplan/00-installer-config.yaml` initially; created manually.
- YAML syntax error during netplan application (resolved by adding `-` for routes).
- Permissions warning on netplan file (fixed with `sudo chmod 600`).
- Deprecated `gateway4` warning in netplan (replaced with `routes`).
- VMware Bridged network alignment with USB-C Ethernet required manual adjustment.

## Next Steps
- **Day 3**: Install and configure CoovaChilli (captive portal) and FreeRADIUS (AAA) services on the Ubuntu VM.
- Develop and deploy the Custom Captive Portal on the Ubuntu VM.
- Design the Website with pricing, FAQs, and vendor onboarding features.
- Build the Mobile App for connectivity and marketplace access.
- Test user authentication workflows and scalability of the network.

## Reflections
- Day 2 successfully established a functional network with pfSense, Ubuntu, and OpenWrt, providing a foundation for future service deployment.
- Netplan configuration challenges improved understanding of Linux networking.
- Connectivity tests (ping and SSH) confirmed the network’s readiness for installing CoovaChilli and FreeRADIUS.
- Comprehensive documentation updates, including screenshots, enhance project transparency and future troubleshooting.
- Pending installation of CoovaChilli and FreeRADIUS will be the focus for Day 3.